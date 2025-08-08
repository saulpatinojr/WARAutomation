#!/bin/bash
#
# Phase 1: AWS Resource Discovery Script for Atlas Assessment
#
# This script performs a comprehensive, read-only discovery of AWS resources.
# It requires the AWS CLI and jq to be installed and configured with appropriate
# read-only and security audit permissions.
#

set -e
set -o pipefail

# --- Configuration ---
# The AWS profile to use from your ~/.aws/credentials file
AWS_PROFILE="default"
# The primary AWS region where your Resource Explorer index is located
PRIMARY_REGION="us-east-1"
# The output file for the standardized JSON data
OUTPUT_FILE="discovery_output_aws.json"

# --- Script Start ---
echo "Starting AWS resource discovery for profile: $AWS_PROFILE"
echo "Output will be saved to: $OUTPUT_FILE"

# Initialize the output file with an opening bracket for the JSON array
echo "
echo "Phase 1.1: Performing broad discovery with AWS Resource Explorer 2..."
all_resources=$(aws resource-explorer-2 search --query-string "*" --profile "$AWS_PROFILE" --region "$PRIMARY_REGION" --max-results 1000)

# Process each discovered resource
echo "Phase 1.2: Enriching resource data with service-specific details..."
echo "$all_resources" | jq -c '.Resources' | while read -r resource; do
    resource_arn=$(echo "$resource" | jq -r '.Arn')
    resource_type=$(echo "$resource" | jq -r '.ResourceType')
    resource_region=$(echo "$resource" | jq -r '.Region')
    
    # Skip null or empty ARNs
    if [[ -z "$resource_arn" |

| "$resource_arn" == "null" ]]; then
        continue
    fi

    echo "Processing ARN: $resource_arn"

    # Initialize a base JSON object for the resource
    base_json=$(jq -n \
                  --arg id "$resource_arn" \
                  --arg type "AWS::$resource_type" \
                  --arg location "$resource_region" \
                  '{id: $id, name: null, type: $type, location: $location, tags: {}, properties: {}}')

    # --- Service-Specific Enrichment ---
    # This section adds deep-dive details for key services relevant to WAF pillars.
    
    enriched_json="$base_json"
    
    case "$resource_type" in
        "EC2::Instance")
            instance_details=$(aws ec2 describe-instances --instance-ids $(basename "$resource_arn") --profile "$AWS_PROFILE" --region "$resource_region" --query "Reservations.Instances" 2>/dev/null |

| echo "{}")
            if [[ -n "$instance_details" && "$instance_details"!= "{}" ]]; then
                enriched_json=$(echo "$enriched_json" | jq \
                    --argjson details "$instance_details" \
                    --arg name "$(echo "$instance_details" | jq -r '.Tags | select(.Key=="Name") |.Value // empty')" \
                    '.name = $name | 
                    .tags = ($details.Tags | if. then (map({(.Key):.Value}) | add) else {} end) |
                    .properties.instanceType = $details.InstanceType |
                    .properties.status = $details.State.Name |
                    .properties.publiclyAccessible = ($details.PublicIpAddress!= null) |
                    .properties.publicIpAddress = $details.PublicIpAddress // "" |
                    .properties.encryption = (if $details.BlockDeviceMappings.Ebs.KmsKeyId then "KMS" else "Default" end)')
            fi
            ;;
        "S3::Bucket")
            bucket_name=$(basename "$resource_arn")
            tags=$(aws s3api get-bucket-tagging --bucket "$bucket_name" --profile "$AWS_PROFILE" --query "TagSet" 2>/dev/null |

| echo "")
            encryption=$(aws s3api get-bucket-encryption --bucket "$bucket_name" --profile "$AWS_PROFILE" --query "ServerSideEncryptionConfiguration.Rules.ApplyServerSideEncryptionByDefault.SSEAlgorithm" 2>/dev/null |

| echo '"None"')
            
            enriched_json=$(echo "$enriched_json" | jq \
                --arg name "$bucket_name" \
                --argjson tags "$tags" \
                --arg encryption "$(echo "$encryption" | tr -d '"')" \
                '.name = $name |
                .tags = ($tags | if. then (map({(.Key):.Value}) | add) else {} end) |
                .properties.encryption = $encryption')
            ;;
        "RDS::DBInstance")
            db_instance_identifier=$(basename "$resource_arn")
            db_details=$(aws rds describe-db-instances --db-instance-identifier "$db_instance_identifier" --profile "$AWS_PROFILE" --region "$resource_region" --query "DBInstances" 2>/dev/null |

| echo "{}")
            if [[ -n "$db_details" && "$db_details"!= "{}" ]]; then
                enriched_json=$(echo "$enriched_json" | jq \
                    --argjson details "$db_details" \
                    --arg name "$(echo "$db_details" | jq -r '.DBInstanceIdentifier')" \
                    '.name = $name |
                    .tags = ($details.TagList | if. then (map({(.Key):.Value}) | add) else {} end) |
                    .properties.instanceType = $details.DBInstanceClass |
                    .properties.status = $details.DBInstanceStatus |
                    .properties.publiclyAccessible = $details.PubliclyAccessible |
                    .properties.multiAZ = $details.MultiAZ |
                    .properties.encryption = (if $details.StorageEncrypted then "KMS" else "None" end)')
            fi
            ;;
        # Add other cases for LoadBalancer, VPC, etc. as needed
    esac

    # Append the processed resource to the output file
    if; then
        echo "$enriched_json" >> "$OUTPUT_FILE"
        FIRST_ITEM=false
    else
        echo "," >> "$OUTPUT_FILE"
        echo "$enriched_json" >> "$OUTPUT_FILE"
    fi
done

# Close the JSON array
echo "]" >> "$OUTPUT_FILE"

echo "AWS Discovery Complete. Results are in $OUTPUT_FILE"

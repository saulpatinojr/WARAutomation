#!/bin/bash
#
# Phase 1: GCP Resource Discovery Script for Atlas Assessment
#
# This script uses Google Cloud Asset Inventory for a comprehensive, read-only
# discovery of GCP resources. It requires the gcloud CLI and jq to be installed
# and authenticated.
#

set -e
set -o pipefail

# --- Configuration ---
# The GCP Project ID to scan.
# For broader scope, change --scope to folders/FOLDER_ID or organizations/ORGANIZATION_ID
PROJECT_ID=$(gcloud config get-value project)
SCOPE="projects/$PROJECT_ID"
# The output file for the standardized JSON data
OUTPUT_FILE="discovery_output_gcp.json"

# --- Script Start ---
echo "Starting GCP resource discovery for scope: $SCOPE"
echo "Output will be saved to: $OUTPUT_FILE"

# Use gcloud asset search-all-resources to get a full inventory [7, 3]
# --read-mask='*' ensures we get all available metadata for deep analysis.
echo "Executing gcloud asset search-all-resources..."
gcloud asset search-all-resources \
    --scope="$SCOPE" \
    --read-mask="*" \
    --format="json" | \
# Use jq to transform the output into the standardized Atlas schema
jq '[. | {
    id:.name,
    name:.displayName //.name | split("/") | last,
    type:.assetType,
    location:.location,
    tags:.labels // {},
    properties: {
        instanceType:.additionalAttributes.machineType // null,
        status:.state // null,
        publiclyAccessible: (if.additionalAttributes.networkInterfaces then ([.additionalAttributes.networkInterfaces.accessConfigs? | select(.natIP!= null)] | length > 0) else false end),
        publicIpAddress: (if.additionalAttributes.networkInterfaces then [.additionalAttributes.networkInterfaces.accessConfigs? |.natIP] | first // "" else "" end),
        encryption: (if.additionalAttributes.disk?.kmsKeyName then "CMEK" else "Google-managed" end)
    }
}]' > "$OUTPUT_FILE"

echo "GCP Discovery Complete. Results are in $OUTPUT_FILE"

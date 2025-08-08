#!/bin/bash
#
# Phase 1: Azure Resource Discovery Script for Atlas Assessment
#
# This script uses Azure Resource Graph for efficient, comprehensive, and
# read-only discovery of Azure resources. It requires the Azure CLI and jq
# to be installed and logged in.
#

set -e
set -o pipefail

# --- Configuration ---
# Specify the subscription ID. Leave empty to use the default active subscription.
# For multiple subscriptions, run this script for each one.
SUBSCRIPTION_ID=""
# The output file for the standardized JSON data
OUTPUT_FILE="discovery_output_azure.json"

# --- Script Start ---
echo "Starting Azure resource discovery..."
if; then
    echo "Targeting subscription: $SUBSCRIPTION_ID"
    az account set --subscription "$SUBSCRIPTION_ID"
fi
echo "Output will be saved to: $OUTPUT_FILE"

# KQL query to gather comprehensive resource data [5, 2]
# This query is designed to pull key properties for WAF analysis.
# CAVEAT: This control-plane query will not list data-plane objects like
# individual storage blobs, SQL database rows, or Key Vault secrets. [6]
KQL_QUERY="
Resources

| project id, name, type, location, tags, properties, sku
| extend instanceType = tostring(sku.name),
         status = tostring(properties.provisioningState),
         publiclyAccessible = isnotnull(properties.publicIPAddress) or isnotnull(properties.publicIPAddresses),
         publicIpAddress = tostring(properties.publicIPAddress.ipAddress),
         encryption = tostring(properties.storageProfile.osDisk.encryptionSettings.enabled)

| project
    id,
    name,
    type,
    location,
    tags,
    properties = pack(
        'instanceType', instanceType,
        'status', status,
        'publiclyAccessible', publiclyAccessible,
        'publicIpAddress', publicIpAddress,
        'encryption', encryption
    )
"

echo "Executing Azure Resource Graph query..."
# Execute the query and format the output using jq to match the standard schema
az graph query -q "$KQL_QUERY" --output json | jq '.' > "$OUTPUT_FILE"

echo "Azure Discovery Complete. Results are in $OUTPUT_FILE"

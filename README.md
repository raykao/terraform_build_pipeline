# Terraform Build Pipeline

This "build pipeline" (consider renaming) will allow you to script/run terraform deployments for CI/CD.

## Steps

Refer to [commands.sh](commands.sh)

1. export the [required environment variables](#required-environment-variables)
2. run ```azure-cli login``` with a service principal defined by the environment variables 
3. run ```terraform init``` with flags to define the TF backend storage for TF.state
4. run ```terraform apply``` to deploy TF template resources

## Required Environment Variables

```:bash
# Required for azure-cli login via service principle
AZ_SERVICE_PRINCIPAL_ID
AZ_SERVICE_PRINCIPAL_SECRET
AZ_TENANT_ID


# Required for configuring Azure Blob Storage as the TF Backend for TF.state
TF_VAR_BACKEND_ACCESS_KEY
TF_VAR_BACKEND_STORAGE_ACCOUNT_NAME
TF_VAR_BACKEND_CONTAINER_NAME
TF_VAR_BACKEND_KEY


# Azure resource varibles for this example
TF_VAR_RESOURCE_GROUP_NAME
TF_VAR_LOCATION
```
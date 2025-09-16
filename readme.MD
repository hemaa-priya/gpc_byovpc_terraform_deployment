## GCP BYOVPC TERRAFORM DEPLOYMENT

### Auth Configuration
- Create a Google Service Account
- Assign project Owner role (service and shared vpc project's)
- run the following commands on your terminal
```
gcloud config set auth/impersonate_service_account <GSA-NAME>@<PROJECT>.iam.gserviceaccount.com
export GOOGLE_OAUTH_ACCESS_TOKEN=$(gcloud auth print-access-token)
```
- If you are using service account impersonation then please follow this [guide](service-account-impersonation.MD)

### GCP resources and Workspace creation

- Creates a VPC
- Creates a subnet within the VPC
- Creates a Cloud Nat
- Registers the network configuration in databricks
- Creates a customer managed databricks workspace with the network config created

## Testing the workspace

- Spin up a classic compute once after workspace is created

# Terraform Cloud Getting Started Guide Example

This is an example Terraform configuration intended for use with the [Terraform Cloud Getting Started Guide](https://developer.hashicorp.com/terraform/tutorials/cloud-get-started/cloud-sign-up).

## What will this do?

This is a Terraform configuration that will create a ResourceGroup and VNet in your azure account. 

When you set up a Workspace on Terraform Cloud, you can link to this repository. Terraform Cloud can then run `terraform plan` and `terraform apply` automatically when changes are pushed. For more information on how Terraform Cloud interacts with Version Control Systems, see [our VCS documentation](https://www.terraform.io/docs/cloud/run/ui.html).

## What are the prerequisites?

You must have an Azure account and provide a Service Principal to Terraform Cloud. Terraform Cloud encrypts and stores variables using [Vault](https://www.vaultproject.io/). For more information on how to store variables in Terraform Cloud, see [our variable documentation](https://www.terraform.io/docs/cloud/workspaces/variables.html).

                                     
https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/guides/service_principal_client_secret

The values for `ARM_CLIENT_ID` `ARM_CLIENT_SECRET` `ARM_TENANT_ID` and `ARM_SUBSCRIPTION_ID` should be saved as environment variables on your workspace.
```bash
export ARM_CLIENT_ID="00000000-0000-0000-0000-000000000000"
export ARM_CLIENT_SECRET="12345678-0000-0000-0000-000000000000"
export ARM_TENANT_ID="10000000-0000-0000-0000-000000000000"
export ARM_SUBSCRIPTION_ID="20000000-0000-0000-0000-000000000000"
```

Some tips:
1. Create token in user setting, not Organization Token. The organization API token is used to manage teams, team membership and workspaces. This token does not have permission to perform plans and applies in workspaces.
2. ARM_CLIENT_SECRET is the value after you create Client secrets, not Secret ID.

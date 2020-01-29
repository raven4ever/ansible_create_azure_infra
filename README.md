# Azure VM creation
This Ansible playbook creates a number of VMs in a pre-defined Azure resource group.

## Requirements
On the Ansible machine the package **sshpass** must be installed.

## Execution
Before executing the playbook you need to configure the parameters for the Azure account!

- Using environmental variables
```
export AZURE_CLIENT_ID="xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
export AZURE_SECRET="xxxxxxxxxxxxxxxxx"
export AZURE_SUBSCRIPTION_ID="xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
export AZURE_TENANT="xxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```

- Using the `az login` command
Install the Azure CLI utility using [this](https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest) page.
After the installation, login with your Azure credentials and select the subscription you want to use.

## Configuration
- `resource_group`: the target Azure resource group where all the objects will reside;
- `students`: a list of usernames that will be used for the creation of the VMs;
- `master_password`: the SSH password that will be set to all the VMs;
- `object_tags`: the Azure tags that will be set to all the objects created by the playbook.
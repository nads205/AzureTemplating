# AzureTemplating
AzureTemplatingDemo

I took a few examples from https://github.com/Azure/azure-quickstart-templates and tweaked them:

I didn't configure everything on the same network exactly as requested using the Azure KeyVault.

1. sql_server_azuredeploy.json - creates two SQL servers with failover
2. vm_win_jumpbox.json - deployment of a VM Scale Set of Windows VMs with a jumpbox

Todo:

Azure Key Vault Integration
The Azure Key Vault integration feature will configure your virtual machine to be able to connect to your Azure key vault. It achieves this by installing the latest version of the SQL Server Connector, configuring EKM provider to access Azure Key Vault, and creates the credential to allow you to access your vault. More information on this feature can be found here.

This template can be used to enable or change the configuration of Azure Key Vault Integration.

If you wish to disable this feature, you must edit azuredeploy.json and change "Enable" to be false.

Notable Parameters
Name	Description	Example
sqlAkvCredentialName	AKV Integration creates a credential within SQL Server, allowing the VM to have access to the key vault. Choose a name for this credential	mycred1
sqlAkvUrl	The location of the key vault	https://contosokeyvault.vault.azure.net/
servicePrincipalName	Azure Active Directory service principal name. This is also referred to as the Client ID.	fde2b411-33d5-4e11-af04eb07b669ccf2
servicePrincipalSecret	Azure Active Directory service principal secret. This is also referred to as the Client Secret.	9VTJSQwzlFepD8XODnzy8n2V01Jd8dAjwm/azF1XDKM=

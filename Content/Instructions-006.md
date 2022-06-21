##Summary

The previous lab provided an empty cloud subscription to then complete activities and create Azure based resources.  Therefore would be scenarios that you would 
require some or maybe all services provisioned for the user.  This is where an Azure Resource Manager template comes into play and can be used to provision resources. 
One feature to remember about using a template to provisiuon resources is these resources are provision with elevated access so the template can provision resources that the user would not have the ability to deploy but they can access them.

###Building a Lab Profile with a simple static template

- From within LOD ensure the AzureCloudLab, Lab Profile is being displayed.
- Edit the Lab Profile and use the **SaveAs** function to save the new Lab Profile with a name of AzureWebAppLab
- Edit this new Lab Profile
- On the Cloud page add the Resource Template **LDW - Basic WebAPP** into the resources template section.
- We will run with the Developement ACP
- Save the Lab Profile

>[!KNOWLEDGE] <summary>
Template contents
</summary>
<details>
>```ARM-nocopy
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
   "contentVersion": "1.0.0.0",
    "resources": [
        {
            "apiVersion": "2016-09-01",
            "name": "AppServicePlan1",
            "type": "Microsoft.Web/serverfarms",
            "location": "[resourceGroup().location]",
            "sku": {
                "name": "D1",
                "capacity": 1
        },
            "properties": {
                "name": "AppServicePlan1"
            }
        },
        {
            "apiVersion": "2015-08-01",
            "name": "[concat('WebApp',substring(ResourceGroup().name,14,11))]",
            "type": "Microsoft.Web/sites",
            "location": "[resourceGroup().location]",
            "dependsOn": [
                "Microsoft.Web/serverfarms/AppServicePlan1"
            ],
            "properties": {
                "name": "[concat('WebApp',substring(ResourceGroup().name,14,11))]",
                "serverFarmId": "[resourceId('Microsoft.Web/serverfarms/', 'AppServicePlan1')]",
                "httpsOnly":true
            }
        }
    ]
}
```

###Testing the ARM template

- Launch the Lab Profile @lab.Variable(initials)-AzureWebAppTemplate
- You will notice this takes much longer to provision
- Navigate into your Resource Group.

>[!ALERT] It can still take upto 90 seconds for the resource to become available in Azure so there still might be an error when you view the Resource Group.  Just wait the 0 Seconds and try again.

- Select the Web App (listed as App Service) with a name of WebAppceGroup1
- Copy the Web App URL and paste into a local browser to confirm the Website loads the default Webpage.

- [] This completes the activities for Lab 3 please let your instructor know that you have completed Lab 3

Press **Next** to continue

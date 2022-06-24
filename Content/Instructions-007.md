##Summary

Having built a lab that used a simple method to assign a dynamic name, in this lab we will look how this can be done using parameters, as well as how the Geolocation can be enabled within the Lab Profile to connect users to the closest Azure region.

###Modifying the AzureWebAppLab Lab Profile

- From within LOD ensure the **Azure Web App Lab**, Lab Profile is being displayed.
- Edit the Lab Profile and navigate to the Cloud page
- On the cloud page make the following changes:
    - Add a second Datacenter, maybe try a location closer to you if possible [Azure regions](https://azure.microsoft.com/en-gb/global-infrastructure/geographies/#overview)
    - Remove the **LDW - Basic WebApp** Template
    - Add a new Resource Template **LDW - WebApp with Parameter**  Notice this requires a parameter to be supplied
        - For the Web Server Name use ++WS-&#64;lab.LabInstance.ID++
- We will run with the Development ACP
- Save the Lab Profile

>[!KNOWLEDGE]<summary>
  Template contents
</summary>
<details>
>In this ARM Template notice there is a parameters section near the top and at the bottom there is an Output section.
>
>```ARMTemplate-nocopy
>{
>    "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
>   "contentVersion": "1.0.0.0",
>        "parameters": {
>            "webServerName": {
>            "type": "string"
>    }
>  },
>    "resources": [
>        {
>            "apiVersion": "2021-03-01",
>            "name": "AppServicePlan1",
>            "type": "Microsoft.Web/serverfarms",
>            "location": "[resourceGroup().location]",
>            "sku": {
>                "name": "D1",
>                "capacity": 1
>        },
>            "properties": {
>                "name": "AppServicePlan1"
>           }
>        },
>        {
>            "apiVersion": "2021-03-01",
>            "name": "[parameters('webServerName')]",
>            "type": "Microsoft.Web/sites",
>            "location": "[resourceGroup().location]",
>            "dependsOn": [
>                "Microsoft.Web/serverfarms/AppServicePlan1"
>            ],
>            "properties": {
>                "name": "[parameters('webServerName')]",
>                "serverFarmId": "[resourceId('Microsoft.Web/serverfarms/', 'AppServicePlan1')]",
>                "httpsOnly":true
>            }
>        }
>    ],
>    "outputs": {
>        "webServerFQDN": {
>        "type": "String",
>        "value": "[reference(parameters('webServerName')).defaultHostName]"
>        }
>    }
>}
>```


###Testing the ARM template

- Launch the Lab Profile **Azure Web App Lab**
- Navigate into your Resource Group.
- Did this resource group provision in another geography?  This will depend based on your location, and the locations added to Azure.

>[!ALERT] It can still take up to 90 seconds for the resource to become available in Azure so there still might be an error when you view the Resource Group.  Just wait a couple of minutes and try again.

- Select the Web App (listed as App Service) with a name of WS-@lab.LabInstance.Id
- Notice the Website Name based on the information you suppled in the parameter for the template
- Copy the Web App URL and paste into a local browser to confirm the Website loads the default Webpage.
- Close the Web Site.
- The template also had an Output parameter.  Edit the instructions for the **Azure Web App Lab** Lab Profile from the Burger Menu while the lab is running lab and try to find the **@lab** variable for the output parameter.
    
>[!Hint] <details>
    Look at the @lab menu in the instructions editor.  Do any of the enteries mention the returned value of an output parameter
    </details>

- [] This completes the activities for Lab 4 please let your instructor know that you have completed Lab 4

Press **End** to complete this set of labs.

##Summary

The previous lab provided an empty cloud subscription to then complete activities and create Azure based resources.  Therefore would be scenarios that you would 
require some or maybe all services provisioned for the user.  This is where an Azure Resource Manager template comes into play and can be used to provision resources. 
One feature to remember about using a template to provisiuon resources is these resources are provision with elevated access so the template can provision resources that the user would not have the ability to deploy but they can access them.

###Building a Lab Profile with a simple static template

- From within LOD ensure the @lab.Variable(initials)-AzureCloudLab, Lab Profile is being displayed.
- Edit the Lab Profile and use the **SaveAs** function to save the new Lab Profile with a name of ++@lab.Variable(initials)-AzureWebAppTemplate++
- Edit this new Lab Profile
- On the Cloud page add the Resource Template **LDW - Basic WebAPP** into the resources template section.
- We will run with the Developement ACP
- Save the Lab Profile

###Testing the ARM template

- Launch the Lab Profile @lab.Variable(initials)-AzureWebAppTemplate
- You will notice this takes much longer to provision
- Navigate into your Resource Group **@lab.CloudResourceGroup(ResourceGroup1).Name**.

>[!ALERT] It can still take upto 90 seconds for the resource to become available in Azure so there still might be an error when you view the Resource Group.  Just wait the 0 Seconds and try again.

- Select the Web App (listed as App Service) with a name of WebAppceGroup1
- Copy the Web App URL and paste into a local browser to confirm the Website loads the default Webpage.

- [] This completes the activities for Lab 2 please let your instructor know that you have completed Lab 3

Press **Next** to continue
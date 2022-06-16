##Summary

The previous lab provided an empty cloud subscription to then complete activities and create Azure based resources.  Therefore would be scenarios that you would 
require some or maybe all services provisioned for the user.  This is where an Azure Resource Manager template comes into play and can be used to provision resources. 
One feature to remember about using a template to provisiuon resources is these resources are provision with elevated access so the template can provision resources that
the user would not have the ability to deploy but they can access them.

###Updating the Access Control Policy

- From within LOD ensure the @lab.Variable(initials)-AzureCloudLab, Lab Profile is being displayed.
- Edit the Lab Profile and use the **SaveAs** function to save the new Lab Profile with a name of ++@lab.Variable(initials)-AzureStorageAccountLab++
- Edit this new Lab Profile
- On the **Cloud** page remove the old Access Control Policy and add the policy ++LOD Managed - Only Storage Accounts++
- Save the Lab Profile

###Testing the new Policy

- Launch the Lab Profile @lab.Variable(initials)-AzureCloudLab
- Navigate into your Resource Group **@lab.CloudResourceGroup(ResourceGroup1).Name**

### Lets provision a Storage Account
 - From the Resource Group Overview page click **+ Create**
 - On the right of the Create a resource blade click **Try Our Quickstart center**
 - Select **Store, back up, or archive data**
 - **Create** an Azure Storage account
 
 Fill the form in with the following values:
 
 |||
|---------------|--------------------------|
| Storage Account Name       | ++sa-@lab.LabInstanceId++                      |

- Press **Review and Create**, Followed by **Create**

>[!Knowledge] This will provbision the resource group within a few seconds.  This is allowed because of the Allow Storage Accounts ACP.  Other resource types should be blocked.

- Press **Go to resource** just to confirm the resource exists.

### Lets attempt to provision another service
- Return to the Resource Group (via the Dashboard if needed)
- Create a Web App using the Quick Create function used above

You will need the following values:

 |||
|---------------|--------------------------|
| Name       | ++wapp@lab.LabInstanceId++                      |
| Runtime | PHP 8.0  |

- Press **Review and Create**, Followed by **Create**
- When the deployment is attempted this will generate a large and unslightl error.  But you should notice that within the first few lines it will state this has been IMAGE[**disallowed by policy**](images/image05.jpg)
- Click the **X** at the top right to close the error.

 - End the Lab and make sure you close both Windows just leaving the orghinal **LDW-Jun22-001: 001 LDW - Azure Cloud** lab running and continue.

- [] This completes the activities for Lab 2 please let your instructor know that you have completed Lab 2

Press **Next** to continue

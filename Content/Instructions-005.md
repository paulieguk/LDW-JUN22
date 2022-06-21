##Summary

As you saw in the previous exercise the unrestricted policy allowed any potential resource could be created which could mean extreme costs could be incurred as well as increase the chance of the Azure subscription being abused by a threat actor.  In this exercise we will assume the requirement is to only allow the creation of an Azure Lab Profile that allows Storage Accounts to be created.

###Updating the Access Control Policy

- From within LOD ensure the AzureCloudLab, Lab Profile is being displayed.
- Edit the Lab Profile and use the **SaveAs** function to save the new Lab Profile with a name of ++AzureStorageAccountLab++
- Make this new Lab Profile a favorite so it is easy to find
- Edit this new Lab Profile
- On the **Cloud** page remove the old Access Control Policy and add the policy ++LDW - Only Storage Accounts++

```ACP-nocopy
{
  "if": {
     "not": {
         "field": "type",
         "equals": "Microsoft.Storage/storageAccounts"
         }
     },
     "then": {
         "effect": "deny"
     }
}
```

- Save the Lab Profile

###Testing the new Policy

- Launch the Lab Profile AzureStorageAccountLab
- Navigate into your Resource Group 

### Lets provision a Storage Account
 - From the Resource Group Overview page click **+ Create**
 - On the right of the Create a resource blade click **Try Our Quickstart center**
 - Select **Store, back up, or archive data**
 - **Create** an Azure Storage account
 
 Fill the form in with the following values:
 
 |||
|---------------|--------------------------|
| Storage Account Name       | ++sa-@lab.LabInstance.Id++                      |

 - Press **Review and Create**, Followed by **Create**

>[!Knowledge] This will provbision the resource group within a few seconds.  This is allowed because of the Allow Storage Accounts ACP.  Other resource types should be blocked.

- Press **Go to resource** just to confirm the resource exists.

### Lets attempt to provision another service
- Return to the Resource Group (via the Dashboard if needed)
- Create a Web App using the Quick Create function used above

You will need the following values:

 |||
|---------------|--------------------------|
| Name       | ++wapp@lab.LabInstance.Id++                  |
| Runtime | PHP 8.0  |

- Press **Review and Create**, Followed by **Create**
- When the deployment is attempted this will generate a large and unslightl error.  But you should notice that within the first few lines it will state this has been IMAGE[**disallowed by policy**](images/image05.jpg)
- Click the **X** at the top right to close the error.

- End the Lab and make sure you close both Windows just leaving the orghinal **LDW-Jun22-001: 001 LDW - Azure Cloud** lab running and continue.

- [] This completes the activities for Lab 2 please let your instructor know that you have completed Lab 2

Press **Next** to continue


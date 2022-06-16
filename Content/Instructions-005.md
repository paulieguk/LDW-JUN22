#Applying a Production Access Control Policy

##Summary

As you saw in the previous exercise the unrestricted policy allowed any potential resource could be created which could mean extreme costs could be incurred as well as increase the chance of the Azure subscription being abused by a threat actor.  In this exercise we will assume the requirement is to only allow the creation of an Azure Lab Profile that allows Stirage Accounts to be created.

From within LOD ensure the @lab.Variable(Initials)-AzureCloudLab, Lab Profile is being displayed.

Edit the Lab Profile and use the **SaveAs** function to save the Lab Profile as @lab.Variable(Initials)-AzureStorageAccountLab

On the **Cloud** page change the permission for User1- from Reader to Owner

>[!TIP] As we know from before this cannot be saved without an Access Control Policy being applied.

In the Access Control Policy section click **+ Add Policy**
Press the Search button and select the **LOD Managed - Allow All (DEVELOPMENT ONLY - Azure)**
Save the Lab Profile
Launch the Lab Profile

Navigate into your Resource Group **@lab.CloudResourceGroup(ResourceGroup1).Name**
Using the **Access Control** menu review the users permissions and see the user now has Owner permissions

>[!Tips] <summary>
  Need help on above
  </summary>
  <details>
  From the Dashboard Click Resource Groups This will list the Resource you have access too.  If it generates an error just click on the arrow to the right and the Resource group should be displayed.
Click the Resource Group to enter it and on the left hand menu select Access Control (IAM) Click view my access and notice the results returned. Close the Windows/Blade that appeared with your access in.
</details>

### Lets provision a Storage Account
 - From the Resource Group Overview page click **+ Create**
 - On the right of the Create a resource blade click **Try Our Quickstart center**
 - Select **Store, back p, or archive data**
 - **Create** an Azure Storage account
 
 Fill the form in with the following values:
 
 |||
|---------------|--------------------------|
| Storage Account Name       | ++sa-@lab.LabInstanceId++                      |

- Press **Review and Create**, Followed by **Create**

>[!Knowledge] This will provbision the resource group within a few seconds.  This is allowed because of the Allow All ACP.  You could provision any other resource you would like.  Wheras this provides a great sandbox and test platform costs can quickly run out of control.

- Press **Go to resource** just to confirm the resource exists.

### Lets provision another service
- Return to the Resource Group (via the Dashboard if needed)
- Create a Web App using the Quick Create function used above

You will need the following values:

 |||
|---------------|--------------------------|
| Name       | ++wapp@lab.LabInstanceId++                      |
| Runtime | PHP 8.0  |

- Press **Review and Create**, Followed by **Create**
- Press **Go to resource** just to confirm the resource exists.
- On the Overview Blade of the Web App Copy the URL at the top right

!IMAGE[Web App URL](images/image03.jpg)

- Paste the URL into you local browser and the IMAGE[default home page](images/image04.jpg) should appear 

- End the @lab.Variable(Initials)-AzureCloudLab Lab.


##Summary

During this Lab you will explore applying an Access Control Policy while developing the Azure Cloud lab.  This Policy would not be allowed to be used in Production and would fail a security review.  Using this policy in a development environment ensures you can develop the Azure content before then updating the policy with an appropriate security Policy.

[Skillable Cloud Security Standards Documenation](https://docs.skillable.com/lod/cloud-security/cloud-security-standards.md)

- From within LOD ensure the **AzureCloudLab** Lab Profile is being displayed.
- Edit the Lab Profile.
- On the **Cloud** page change the permission for User1- from Reader to Contributor.

>[!TIP] As we know from before this cannot be saved without an Access Control Policy being applied.

- In the Access Control Policy section click **+ Add Policy**
- Press the Search button and select the **LOD Managed - Allow All (DEVELOPMENT ONLY - Azure)**

```ACP-nocopy
{
"if": {
    "not":{
        "field": "type",
        "like": "Microsoft.*"
        }
    },
    "then": {
        "effect": "deny"
    }
}
```

- Save the Lab Profile

>[!KNOWLEDGE] Notice the Lab Profile now needs a security review.  Skillable would not pass a Lab Profile with an allow all but because this Lab Profile has write capability into Azure it needs to be approved before it can go into production.  Security reviews will be discussed more later.
>!IMAGE[Security Review](images/image06.jpg)


- Launch the Lab Profile
- Navigate into your Resource Group
- Using the **Access Control** menu review the users permissions and see the user now has Contributor permissions

>[!TIP] <summary>
  Need help on above
  </summary>
  <details>
  From the Dashboard Click Resource Groups This will list the Resource you have access too.  If it generates an error just click on the arrow to the right and the Resource group should be displayed.    
Click the Resource Group to enter it and on the left hand menu select Access Control (IAM) Click view my access and notice the results returned. Close the Windows/Blade that appeared with your access in.    
</details>

### Lets provision a Storage Account
 - From the Resource Group Overview page click **+ Create**
 - On the right of the Create a resource blade click **Try Our Quickstart center**
 - Select **Store, back up, or archive data**
 - **Create** an Azure Storage account
 
 Fill the form in with the following values:
 
 |||
|---------------|--------------------------|
| Storage Account Name       | ++sa@lab.LabInstance.Id++                      |


- Press **Review and Create**, Followed by **Create**

>[!Knowledge] This will provbision the resource group within a few seconds.  This is allowed because of the Allow All ACP.  You could provision any other resource you would like.  Whereas this provides a great sandbox and test platform costs can quickly run out of control.

- Press **Go to resource** just to confirm the resource exists.

### Lets provision another service
- Return to the Resource Group (via the Dashboard if needed)
- Create a Web App using the Quick Create function used above

You will need the following values:


 |||
|---------------|--------------------------|
| Name       | ++wapp@lab.LabInstance.Id++                      |
| Runtime | PHP 8.0  |

- Press **Review and Create**, Followed by **Create**
- Press **Go to resource** just to confirm the resource exists.
- On the Overview Blade of the Web App Copy the URL at the top right

!IMAGE[Web App URL](images/image03.jpg)

- Paste the URL into your local browser and the IMAGE[default home page](images/image04.jpg) should appear 

- End the AzureCloudLab Lab.

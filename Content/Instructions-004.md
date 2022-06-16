#Summary

During this Lab you will explore applying an Access Control Policy while developing the Azure Cloud lab.  This Policy would not allowed to be used in Production and would fail a security review, but ensures you can develope the Azure content before then updating the policy with an appropiate security Policy.

From within LOD ensure the @lab.Variable(Initials)-AzureCloudLab, Lab Profile is being displayed.

Edit the Lab Profile.

On the **Cloud** page change the permission for User1- from Reader to Owner

>[!TIP] As we know from before this cannot be saved without an Access Control Policy being applied.

In the Access Control Policy section click **+ Add Policy**
Press the Search button and select the **LOD Managed - Allow All (DEVELOPMENT ONLY - Azure)**
Save the Lab Profile
Launch the Lab Profile

Navigate into your Resource Group **@lab.CloudResourceGroup(ResourceGroup1).Name**

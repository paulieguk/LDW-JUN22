
## Summary
You will build an Azure Lab Profile with the absolute minimal settings

- From the Skillable Dashboard Create a new lab profile then from the Template Gallery use the **+ Create Custom Environment** option.  When creating the new Lab Profile use the following information:

**Basic Page**

|||
|---------------|--------------------------|
| Number:       | ++@lab.Variable(initials)++                      |
| Name:         | ++AzureCloudLab++ |
| Organisation: | LDW-JUN22                |
| Series:       | LDW-JUN22                |
| Virtualization Platform: | None |

**Cloud Page**

|||
|---------------|--------------------------|
| Cloud Platform:       | Azure                     |
| Subscription Pool:    | Career RockIT (Skillable) |
| Datacenter Availability | East US 2 |

>[!Knowledge] This represents the minimum data that can be entered into an Azure Cloud Lab Profile.  Notice there was already a user selected with a prefix of **User1-**

- Save the Lab Profile.
- From the top of the Lab Profile click the **Favourite** star

>[!Alert] If you have your own Azure Accounts you might get prompted to log in with those.  DO NOT.  Ensure you only log in with the provided credentials!

 - Launch and enter the Lab, signing in with the credentials provided on the resource tab.

>[!NOTE]Notice you cannot do anything even browsing is limited, when you entered Azure might have displayed a subscription error. 
If you navigate anywhere Azure just tries to get you to sign up for a trial.  

 - End the Lab and make sure you close both Windows just leaving the original **LDW-Jun22-001: 001 LDW - Azure Cloud** lab running and continue.

>[!KNOWLEDGE] This is the way CSS would be enabled and the User would have full access to the subscription.  But the subscription **Career RockIT (Skillable)** is 
setup as shared and therefore is used for CSR.

!IMAGE[Azure Subscription Pool](images/image01.jpg)

Press **Next** to continue

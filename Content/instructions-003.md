## Summary
So in this exercise you will add some more settings to enable CSR and test that security.

From the LOD Dashboard select the Lab Profile ++@lab.Variable(initials)-BasicAzure++ and edit that profile.

On the **Cloud page** make the following changes.

|||
|---------------|--------------------------|
| Number:       | ++001++                      |
| Name:         | ++@lab.Variable(initials)-BasicAzure++ |
| Organisation: | LDW-JUN22                |
| Series:       | LDW-JUN22                |
| Virtualization Platform: | None |

**Cloud Page**

|||
|---------------|--------------------------|
| Cloud Platform:       | Azure                     |
| Subscription Pool:    | Career RockIT (Skillable) |
| Datacenter Availability | US East 2 |

>[!Knowledge] This represents the minimum data that can be entered into an Azure Cloud Lab Profile.  Notice there was already a user selected with a prefix of **User1-**

>[!Alert] If you have your own Azure Accounts you might get prompted to log in with those.  DO NOT.  Ensure you only log in with the provided credentials!

Launch and enter the Lab, signing in with the credentials provided on the resource tab.

Notice you cannot do anything, when you entered Azure it might have showed a subscription error. 
If you navigate anywhere Azure just trys to get you to sign up for a trial.  

 - End the Lab

This is the way CSS would be enabled and the User would have full access to the subscription.  But the subscription **Career RockIT (Skillable)** is 
setup as shared and therefore is used for CSR.

!IMAGE[Azure Subscription Pool](images/image01.jpg)

Press **Next** to continue

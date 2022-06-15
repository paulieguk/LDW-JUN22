From the Skillable Dashboard Create a new lab profile using the **+ Create Custom Environment** option from the Template Gallery.  When creating the new Lab Profile use the following information:

**Basic Page**

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

Notice you cannot do anything, when you entered the system errored and if you navigate anywhere Azure just trys to get you to setup a trial.  
This is the way CSS would be enabled and the User would have full access to the subscription.  But the subscription **Career RockIT (Skillable)** is 
setup as shared and therefore is used for CSR.



!IMAGE[Search Results](images/ak02lpo7.jpg)

1. [] Scroll down the details page and notice the information provided.  Especially focuses on the version list, we will use this later.

### Review Container Options

1. [] In LabOnDemand navigate to the Admin Page
1. [] Notice the options in the Containers box, they should look like below

!IMAGE[4rdrj25l.jpg](images/4rdrj25l.jpg)

@lab.Activity(Question2)

---

1. [] In the Containers tile, select **Container Registries** and press **Search**  
1. [] Notice the **ldw-feb2022** Registry.  Click **Edit**
    - Notice this Registry is hosted on the Docker Hub
    - It supports **Private** stores which is defined by the need for credentials
1. [] Review the [Skillable Help](https://docs.learnondemandsystems.com/lod/container-registries.md?appid=lod), focusing on the following:
    - Address
    - Allow Push
    - Use Admin Account
1. [] Click **Cancel** (bottom left) or **Details** (top right).  We will use a prebuilt Registry

Press **Next** to continue

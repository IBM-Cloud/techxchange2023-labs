 Setup Administrator Account

## Understanding the IBM Cloud Basics

In this lab we will cover a few topics and it's important to understand how they come together.  We will be interacting with [IBM Cloud Accounts](https://cloud.ibm.com/docs/account?topic=account-accounts), [Identity and Access Management (IAM)](https://cloud.ibm.com/docs/account?topic=account-account_setup), [Infrastructure as Code (IaC)](https://cloud.ibm.com/docs/schematics?topic=schematics-infrastructure-as-code), and [Security and Compliance Center (SCC)](https://cloud.ibm.com/docs/security-compliance?topic=security-compliance-best-practices).

Each one of these components plays a critical role in ensure your organization is optimized for efficient workflows that meet the compliance standards of heavily regulated industries.


## Enterprise Accounts

1. From the **Dashboard** and located on the **Top NavBar** Click **Manage**.
1. Select the **Enterprise** from the dropdown.
   1. You should see that your account belongs to the Enterprise `TechZoneEnterprise`.  Under normal circumstances, this would most likely be your company name.
![](images/20-show-enterprise.png ':size=400')

You can familiarize yourself with the enterprise architecture with the help of the [Enterprise White Paper](https://cloud.ibm.com/docs/enterprise-account-architecture?topic=enterprise-account-architecture-account-structure).

## Identity and Access Management
Now lets Navigate to [IAM Overview](https://cloud.ibm.com/iam/overview) to understand IAM's functionalities. You can find an introduction to IAM concepts, which covers access groups, users, trusted profiles in IBM Cloud Documentation. For further details, refer to [IAM Concepts](https://cloud.ibm.com/docs/account?topic=account-cloudaccess).

1. From the **Dashboard** and located on the **Top NavBar** Click **Manage**.
1. Select the **IAM** from the dropdown.

![](images/20-iam.png ':size=400')

Here you can manage additional users, trusted profiles, API Keys, Access groups and more.



## Trusted Profiles
Let's review your trusted profiles at [Trusted Profiles](https://cloud.ibm.com/iam/trusted-profiles) in the **Left Navigation**

![](images/20-trusted-profiles.png ':size=400')

Here you can create trusted profiles to automatically grant federated users access to your account based on external identity provider specifications

## Access Groups


Now let's investigate access groups by visiting [Access Groups](https://cloud.ibm.com/iam/groups) in the **Left Navigation**

Here you create access groups to quickly and easily assign access to a set of users, service IDs and trusted profiles. To add identities and assign access to an existing group, click the group name.

![](images/20-access-groups.png ':size=400')

1. From the list, select `da-lab-2048-administrator`
1. From the Group Details page, select the **Access** tab

![](images/20-access-group-permissions.png ':size=400')

Here you can view all of the permissions that are granted to this access group.





⇨ [Now let's set up a Scan as a Compliance Officer](25-compliance.md)

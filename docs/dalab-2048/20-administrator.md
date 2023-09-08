# Assign and monitor access as Administrator

As you work through this lab, you will select a different trusted profile that corresponds to each role within Hill Valley Bank. Let's start with the **Administrator** role.

Access Managers assign and monitor access among human users and non-human identities (like programs, APIs, etc.) in a cloud environment.

## Log in as Administrator

1. Go to https://ibm.biz/lab2048-invite.
1. Enter the `Username` and `Password` provided for the lab.
1. Click **Sign in**.
  ![](images/20-lab-login.png ':size=400')
1. You must provide a trusted profile. **Select** the trusted profile tile labeled **Administrator**
  ![](images/20-select-profile.png ':size=400')
1. You should now be successfully logged in as an **Administrator** on the **IBM Cloud Dashboard**.
  ![](images/20-dashboard.png ':size=400')

## Enterprise Accounts

1. From the **Dashboard** and located on the **Top NavBar** Click **Manage**.
1. Select the **Enterprise** from the dropdown.
   1. You should see that your account belongs to the Enterprise `TechZoneEnterprise`.  Under normal circumstances, this would most likely be your company name.
![](images/20-show-enterprise.png ':size=400')

?> You can familiarize yourself with the enterprise architecture with the help of the [Enterprise White Paper](https://cloud.ibm.com/docs/enterprise-account-architecture?topic=enterprise-account-architecture-account-structure).

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

⇨ [Define compliance rules as Compliance Manager](25-compliance.md)

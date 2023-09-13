# Assign and monitor access as Administrator

Administrators act as *Access Managers* to assign and monitor access among human users and non-human identities (like programs, APIs, etc.) in a cloud environment. Their responsibilities include:
* Evaluating access needs;
* Assigning and automating access types;
* Monitoring and updating access as environment evolves.

As you work through this lab, you will select a different trusted profile that corresponds to each role within Hill Valley Bank. Let's start with the **Administrator** role. You will walk through the identity and access management concepts and review the configuration that was prepared for the lab. There are no changes to be done in this section.

## Log in as Administrator

### Retrieve the credentials to use for authentication

1. From the desktop of the _jumpbox_ machine, open the file named `password.txt`. It contains the `Username` and `Password` to use for authentication.
   ![](images/10-password.png ':size=400')
1. Keep the file open for the next steps.

### Log in

1. Go to https://ibm.biz/lab2048-invite.
1. Enter the `Username` and `Password` provided for the lab.
1. Click **Sign in**.
  ![](images/20-lab-login.png ':size=400')
1. You must provide a trusted profile. **Select** the trusted profile tile labeled **Administrator**
  ![](images/20-select-profile.png ':size=400')
1. You should now be successfully logged in as an **Administrator** on the **IBM Cloud console**.
  ![](images/20-dashboard.png ':size=400')

## Basic account configuration

Part of the responsibilities for the Administrator will be to provide contact information for the account, to configure licenses acquired through IBM Passport Advantage, to define global notification lists, to create resource groups where engineers can deploy resources.

All these options are found under the global **Account page**.
1. Go to https://cloud.ibm.com/account to access the configuration of the Account.
   * Alternatively, use the top menu to go to **Manage** > **Account**.

## Enterprise configuration

Larger organizations usually rely on multiple accounts. These accounts belong to an Enterprise and grouped in account groups.

![](images/20-enterprise-hierarchy.svg ':size=800')

The account you are accessing today is part of a larger enterprise. To view the details of the Enterprise the account belongs to:
1. Go to https://cloud.ibm.com/enterprise.
   * Alternatively, use the top menu to go to **Manage** > **Enterprise**.

## Identity and Access Management

Access and permissions are defined by Identify and Access Management (IAM). With IAM, you can manage additional users, trusted profiles, API Keys, Access groups and more.
   ![](images/20-iam.png ':size=400')

1. Go to https://cloud.ibm.com/iam/overview to access IAM.
   * Alternatively, use the top menu to go to **Manage** > **Access (IAM)**.
1. In the left menu, select **[Trusted profiles](https://cloud.ibm.com/iam/trusted-profiles)**. Trusted profiles are used to automatically grant federated users access to your account based on external identity provider specifications. This is how this lab is configured! 3 trusted profiles were created, providing your user with 3 different profiles to adopt with only one set of credentials. As the **Administrator**, you are currently assigned the `da-lab-2048-administrator` profile.
   ![](images/20-trusted-profiles.png ':size=400')
1. Now select **[Access Groups](https://cloud.ibm.com/iam/groups)**. Access groups allow to quickly and easily assign access to a set of users, service IDs and trusted profiles. As the **Administrator**, you have been added to the `da-lab-2048-administrator` access group.
   ![](images/20-access-groups.png ':size=400')
1. Click on the access group.
1. Click on the **Access** tab to view the permissions defined for this group.
   ![](images/20-access-group-permissions.png ':size=400')

Your task as **Administrator** is complete.

⇨ [Define compliance rules as Compliance Manager](25-compliance.md)

# Define compliance rules as Compliance Manager

The Engineer will be deploying resources in a specific resource group. As Compliance Manager, you are going to configure a custom profile and an attachment to assess the deployed resources.
   * A profile is a collection of related controls that you can use to evaluate your organization's compliance posture. In this custom profile, you will be selecting a very specific rule that ensures encryption is enabled for data at rest.
   * An attachment is the connection between a profile and a set of resources that defines the way an evaluation is conducted.

## Log in as Compliance Manager

1. Log out from the IBM Cloud console.
  ![](images/25-logout.png ':size=400')
1. Go to https://ibm.biz/lab2048-invite.
1. Enter the `Username` and `Password` provided for the lab.
1. Click **Sign in**.
1. **Select** the trusted profile tile labeled **Compliance Manager**.
1. You should now be successfully logged in as an **Compliance Manager** on the **IBM Cloud console**.

## Define a custom profile with specific compliance controls

1. Go to Security and Compliance at https://cloud.ibm.com/security-compliance/overview.
   * Alternatively, use the navigation menu to go to the Security and Compliance Overview page: ☰ > Security and Compliance > Overview.
1. Select **Profiles** in the left menu.
1. Click **Create**.
1. In **Details**:
   1. Set **Name** to `<your-username>`. As example `dalab-123`.
   1. Set **Version** to **1.0.0**.
   1. Set **Description** to **Controls for my organization**.
   1. Click **Next**.
1. In **Controls**:
   1. Click **Add**.
   1. Select **IBM Cloud for Financial Services**.
   1. Click **Next**
   1. Search the control named `SC-28(1)(0)`. This control requires components of a system to use encryption.
   1. Select the control.
      ![](images/25-select-controls.png ':size=400')
   1. Click **Add**.
   1. Back to the **Controls** table, click **Next**.
1. In **Parameters**, click **Next**. The control you selected has no specific parameters to configure.
1. In **Review**, click **Create**.

The description of the control `SC-28(1)(0)` reads as _The information system implements cryptographic mechanisms to prevent unauthorized disclosure and modification of [confidential customer data] on [organization-defined information system components including portable computers, mobile devices, and electronic removable media]._ In IBM Cloud, this will translate as a requirement to enable encryption using customer-managed keys (Keep Your Own Key - KYOK) for all services that support encryption.
   ![](images/25-control-description.png ':size=600')

?> The IBM Cloud for Financial Services library contains more than 500 controls defined in collaboration with financial institutions.

## Create an attachment to evaluate the resources deployed by the Engineer

Once the profile is created, you can create an attachment.

1. From the **Actions** menu, select **Attach**.
1. In **Details**, set the **Name** to `<your-username>-encryption-only`, as example `dalab-123-encryption-only`.
1. Click **Next**.
1. In **Profile**, confirm the **Profile** is the one you created in the previous step.
1. Click **Next**.
1. In **Scope**, select the entry named after your username, as example `dalab-123`. This entry refers to the _resource group_ where the Engineer will deploy resources.
1. Click **Next**.
1. In **Scan settings**, uncheck **Enable scan**. This gives the ability to configure the frequency at which you want to evaluate your selected resources. In this lab, you will run the scan on demand so you don't need to activate that option.
1. Click **Next**.
1. Click **Create**.
   ![](images/25-create-attachment.png ':size=600')

?> With the ability to run the evaluation daily, you can assess your compliance posture continuously and take immediate actions when non-compliant configurations are detected.

At this stage, no resources have been deployed in the Engineer but your controls are in place. Time to become an Engineer and to deploy resources in the cloud!

⇨ [Continue with Engineer section](30-engineer.md)

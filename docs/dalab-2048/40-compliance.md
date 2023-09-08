# Assess the compliance as Compliance Manager

As Compliance Manager, your role is to:
* identify what resources need to be compliant with which regulations,
* gather evidence during an audit,
* maintain visibility into compliance posture.

The Engineer has deployed some resources. Let's assess the compliance of these resources.

## Log in as Compliance Manager

1. Log out from the IBM Cloud console.
1. Go to https://ibm.biz/lab2048-invite.
1. Enter the `Username` and `Password` provided for the lab.
1. Click **Sign in**.
1. **Select** the trusted profile tile labeled **Compliance Manager**.
1. You should now be successfully logged in as an **Compliance Manager** on the **IBM Cloud console**.

## Run scan

1. Go to Security and Compliance at https://cloud.ibm.com/security-compliance/overview.
   * Alternatively, use the navigation menu to go to the Security and Compliance Overview page: ☰ > Security and Compliance > Overview.
1. Select **Attachments** in the left menu.
1. Locate the attachment you created earlier and from the Actions menu (︙) on the right, select **Run scan**.
   ![](images/40-run-scan.png ':size=400')

## While you wait...

The scan may take a few minutes. In the meantime, you can inspect existing scan results.

1. Look for the attachment named **all-resources-in-the-account** in the list. This attachment is based on the IBM Cloud for Financial Services profile. It performed an evaluation of the 500+ controls defined in the profile.
1. From the Actions menu (︙) on the right, select **View scan results**.
1. Click on the result named **all-resources-in-the-account**.
   ![](images/40-view-all-resources-results.png ':size=400')

In preparation of the lab, a large architecture based on Red Hat OpenShift on Cloud was deployed in this account. This deployable architecture is made of more than 100 resources that were scanned as part of the evaluation. In this scan results, 67% of the resources were detected as compliant -- the scan included all resources in the account.

Drilling down in the list of resources, you can identify why a specific resource is not compliant. Based on the controls, you would typically work with the team in charge of the resource to remediate the issue.

## View your results

Your scan should have completed.

1. Go to Security and Compliance at https://cloud.ibm.com/security-compliance/overview.
   * Alternatively, use the navigation menu to go to the Security and Compliance Overview page: ☰ > Security and Compliance > Overview.
1. Select **Attachments** in the left menu.
1. Locate the attachment you created earlier and from the Actions menu (︙) on the right, select **View scan results**.
1. Select the scan results in the table.
   ![](images/40-view-my-result.png ':size=400')

The scan included 1 (one) control `SC-28(1)(0)` defined as _The information system implements cryptographic mechanisms to prevent unauthorized disclosure and modification of [confidential customer data] on [organization-defined information system components including portable computers, mobile devices, and electronic removable media]_.

![](images/40-my-result-overview.png ':size=400')

If you switch to the **Resources** tab, you will find the Cloud Object Storage buckets created by the Engineer. The buckets do not have encryption enabled. There are not compliant with the profile controls.
   ![](images/40-my-result-resources.png ':size=400')

If this was in your organization, now would be a good time to go have a talk with the Engineer to find out how these non-compliant resources can be made compliant 😉

⇨ [Continue with the Conclusion](50-conclusion.md)

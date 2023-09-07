# Getting Started

Lets get ready! We are going to collaboratively set up a secure and compliant cloud for Hill Valley Bank.  First we are going to play the role of an Administrator where we will prepare the account for enterprise governance by establishing trust and assigning access to federated users. Second, we are going to transition to the Engineer role, where we will deploy are brand new OpenShift Environment following best practices for a banking Environment. Lastly, we will play the role of a Compliance Manager who will define and assess our continuous compliance posture of our bank.


**In this lab, you will:**
1. Create a compliance Scan
1. Create a new IaC configuration and store it in a private catalog
1. Deploy your configuration using IBM Cloud Projects
1. Run the compliance scan you crated on your deployment

**Lets get started!**

## Log in to IBM Cloud

1. Go to https://ibm.biz/lab2048-invite.
1. Enter the `Username` and `Password` provided for the lab.
  ![](images/10-lab-login.png ':size=400')
1. Click **Sign in**.

1. You must provide a trusted profile. As you work through this lab, you will select a different trusted profile that corresponds to each role within Hill Valley Bank. Lets start by selecting the **Administrator** role.

 **Select** the trusted profile tile labeled **Attendee for IBM TechXchange 2023**
  ![](images/10-select-trusted-profile.png ':size=400')

You should now be successfully logged in as an **Administrator** on the **IBM Cloud Dashboard**.

  ![](images/20-dashboard.png ':size=400')

⇨ [Continue to Administrator](20-administrator.md)

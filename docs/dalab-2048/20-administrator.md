 Administrator

### Start with Slides

![Slides](images/01-slides.png)

- Kickstart with a non-interactive session using slides.
- Understand the workflow based on account management, IAM, IAC, and SCC.
- Dive into an enterprise account structure, encompassing enterprise, account groups, and accounts.
- Introduction to IAM concepts, which covers access groups, users, trusted profiles. For further details, refer to [IAM Concepts](https://cloud.ibm.com/docs/account?topic=account-cloudaccess).
- Familiarize yourself with the enterprise architecture with the help of the [Enterprise White Paper](https://cloud.ibm.com/docs/enterprise-account-architecture?topic=enterprise-account-architecture-account-structure).
- The lab.md file captures most of the session so that participants can review post-session.

### Review the Account Configuration

- Confirm your position within an enterprise at [IBM Cloud Enterprise](https://cloud.ibm.com/enterprise).
- Navigate to [IAM Overview](https://cloud.ibm.com/iam/overview) to understand IAM's functionalities.
- Review trusted profiles at [Trusted Profiles](https://cloud.ibm.com/iam/trusted-profiles).
- Investigate access groups by visiting [Access Groups](https://cloud.ibm.com/iam/groups).
- Examine the IAM permissions exclusively set for the lab.

### Compliance

Ensure that the compliance service is already provisioned and set up in advance.

- Run the pre-created scan on the SLZ to gauge compliance in the ROKS environment.

### About SCC

Get an introduction to SCC. Proceed to [SCC Overview](https://cloud.ibm.com/security-compliance/overview) to understand its steps:

1. Define your requirements.
2. Implement secure deployments.
3. Assess your posture.

### Create a Scan to Assess the Engineer Work

- Head to SCC.
- Design a custom profile emphasizing the control SC-28(1)(0).
- Under Attachments, label it as "dalab-01-scan".
- Select the custom profile and choose the dalab-01 resource in Scope.
- Disable the automatic scan. Initiate it manually when needed.

⇨ [Continue with Engineer section](30-engineer.md)

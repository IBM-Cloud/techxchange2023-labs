# Customize the image

In this section you will test the custom image that you just created by creating a Virtual Server Instance (VSI).

You will also add a unique **cloud-init** script that will be executed during the initial start up of the operating system.  Finally you will verify that the VSI is working properly by accessing it via a floating IP address that you will assign.

At the end of this section you will have a VSI running with unique contents that can be saved as a VPC image in the next section!

## Generate your SSH key

An SSH key is a required prerequisite to creating a VSI.  Let's create a new one now just in case you need to access this VSI in the future.

1. Go to https://cloud.ibm.com/vpc-ext/compute/sshKeys.
   * Alternatively, use the navigation menu to go to the SSH keys page: ☰ > VPC Infrastructure > SSH keys.
1. Click **Create**.
1. Set **Geography** to **North America**.
1. Set **Region** to **Dallas**.
1. Set **Name** to `<your-username>-key`. As example `vpclab-123-key`.
1. Keep the default value for **Resource group**.
1. Set **SSH key type** to **rsa**.
1. Select **Generate a key pair for me** as the SSH key input method.
1. Click **Save private key**.
1. Save the `.prv` file. Make sure to remember the location where you saved the file as you will need it to access the VSI.
1. Click **Save public key**.
1. Save the `.pub` file.
1. Click **Create**.

## Create an instance from the custom image

You will create a VSI from the custom image and customize the instance during the provisioning. The customization will install the `nginx` server and modify its homepage.

1. Go to https://cloud.ibm.com/vpc-ext/compute/vs.
   * Alternatively, use the navigation menu to go to the Virtual server instances page: ☰ > VPC Infrastructure > Virtual server instances.
1. Select **Dallas** as the target region.
1. Click **Create**.
1. Set **Architecture** to **Intel**.
1. Under **Location**
   1. Set **Geography** to **North America**.
   1. Set **Region** to **Dallas**.
   1. Set **Zone** to **Dallas 2**.
1. Set **Name** to `<your-username>-vsi-v1`. As example `vpclab-123-vsi-v1`.
1. Keep the default value for **Resource group**.
1. Under **Image and profile**, click **Change image**.
   1. Select the **Custom images** tab at the top.
   1. Select the image named after your username (as example `vpclab-123-v1`).
   1. Click **Select**.
   ![](images/20-vsi-change-image.png ':size=500')
   ![](images/20-vsi-custom.png ':size=500')
1. Under **Profile**, click **Change profile**.
   1. Check **Compute** under **Category**
   1. Select **cx2-2x4** as the the profile.
   1. Click **Save**.
   ![](images/20-select-profile.png ':size=500')
1. Under **SSH keys**, select `labadmin` and the SSH key you created (as example `vpclab-123-key`).
1. Scroll down to **Advanced options**.
   1. Open the **User data** twisty.
   1. Copy and paste the following.  
   ```sh
   #!/bin/sh
   set -x
   DEBIAN_FRONTEND=noninteractive apt-get --yes update
   DEBIAN_FRONTEND=noninteractive apt-get --yes install nginx
   echo USERNAME version 1 > /var/www/html/index.nginx-debian.html
   ```
   1. Change `USERNAME` with your username (as example `vpclab-123`)
  ![](images/20-vsi-user-data.png ':size=400')
1. Click **Create virtual server**.

?> The above script will be executed during the provisioning of the virtual server instance by `cloud-init`. It is a simple way to inject customization into a virtual server instance.

## Make the instance visible on the Internet

You will verify that the instance has been provisioned and contains the unique content you added in the user data. To access the VSI, a floating IP is required.

1. Select the VSI you created. It is named after your username (as example `vpclab-123-vsi-v1`).
1. Scroll down to **Network interfaces** and click the **Edit** pencil.
  ![](images/20-fip.png ':size=400')
1. In the Floating IP address
   1. Select an existing Floating IP named after your usage (as example `vpclab-123-fip`)if available
   1. If none available, choose **Reserve a new floating IP** from the drop down.
      ![](images/20-fip-select.png ':size=400')
1. Click **Save**.
1. In the **Network interfaces**, click on the **Floating IP** assigned to your virtual server instance to copy the value to the clipboard.

## Verify the instance is using your image and start up code

1. Open a new browser tab.
1. Access the `nginx` web site at `http://Floating_IP` replacing `Floating_IP` with the value you copied before.
1. Check the contents match your username.
   ![](images/20-nginx.png ':size=400')

!> If you are not getting the correct results see the **Troubleshooting** section below. Otherwise skip to the [next section](30-capture-modifications.md).

[⇨ Continue to Capture modifications](30-capture-modifications.md)

### Troubleshooting

If the browser attempt to access the floating IP is not returning the expected results, here are some things to check on the virtual server instance details page:
1. Verify the VSI is in the **Running** state.
1. Verify that the **Image** section specifies your `<your-username>-vsi-v1` image.
1. Verify the **Network interfaces** has the **Floating IP** and you are attempting to access that floating IP.

Another option is to connect to the virtual server instance with SSH.
1. Open a terminal window.  On a Linux jump box, click **Activities**, click **Terminal**.
1. The SSH private key file must have permissions `r--------` to be used by SSH. The downloaded VPC SSH key and was created in the previous section and could be in a different directory depending on your workstation's operating system.
   ```sh
   chmod 400 ~/Downloads/vpclab123_rsa.prv
   ```
1. Connect to the VPC instance using the **Floating IP** created above. The Floating IP is the floating IP address copied in the previous step.
   ```
   ssh -i ~/Downloads/vpclab123_rsa.prv root@Floating_IP
   ```
1. Look at the log files
   ```
   cd /var/log
   more cloud* messages*
   ```
1. Log out of terminal.
   ```
   logout
   ```

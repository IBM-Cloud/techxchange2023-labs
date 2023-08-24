# Capture modifications

The VSI instance boot volume was initialized from your Debian 10 **cloud-init** enabled image. The boot disk was modified during initialization by the script passed as `user-data`. This VSI is now running nginx and serving a unique file. It is a very simple modification of the base Debian 10 image but enough to highlight the typical lifecycle of creating custom images.

In this section you will create a VPC image from your modified boot volume.
   ![](images/version-100.svg ':size=600')

?> Keep in mind that it is possible to set up an automated CI/CD pipeline to create VPC images and integration with tools like [Packer](https://www.packer.io/), the [IBM Packer Plugin](https://github.com/IBM/packer-plugin-ibmcloud) and [ansible](https://www.ansible.com/).<br><br>
For example, in an enterprise environment, you might use automation to create golden images that should be used by all virtual server instances in your company or used as the basis to create application-specific immutable images. Golden images are typically used to implement company-wide best practices and security policies.

## Create version 2 of your image

In this section, you capture a new version of your image from the boot volume of the instance you provisioned.

1. Go back to your virtual server instance page in IBM Cloud console.
1. From the **Actions** menu, choose **Stop**.
   ![](images/30-actions.png ':size=400')
1. Click **Stop** in the confirmation dialog.
1. Wait for the instance to be stopped.
1. From the **Actions** menu, choose **Create image**.

In the _Custom image for VPC_ dialog:
1. Set **Geography** to **North America**.
1. Set **Region** to **Dallas**.
1. Set **Name** to `<your-username>-v2`. As example `vpclab-123-v2`.
1. Keep the default value for **Resource group**.
1. Ensure **Virtual server instance boot volume** is selected as **Image source**.
1. Ensure your virtual server instance is selected too.
1. Click **Create custom image**.
1. Wait for the image to become **Available**.

?> At this stage, you have created a new custom image from your virtual server. The image can be used to create new virtual server instances. They would contain all the modifications you may have done to the original virtual server before you created the image.

## Delete the instance

1. Go to https://cloud.ibm.com/vpc-ext/compute/vs.
   * Alternatively, use the navigation menu to go to the Virtual server instances page: ☰ > VPC Infrastructure > Virtual server instances.
1. Select your virtual server instance.
1. From the **Actions** menu, choose **Delete**.
1. Follow confirmation instructions.

## Obsolete the initial image

You can control the complete lifecycle of your images. As example, once you release a new version of an image you may want to mark the previous version as _Deprecated_, or _Obsolete_ so that users in your account migrate to the most recent version. It is a nicer approach than simply deleting the previous version and give users some grace period before they can't use the previous version anymore.

A _Deprecated_ image can still be used to create new instance, where an _Obsolete_ image can not. Both will still show in the list of available custom images.

1. Go to https://cloud.ibm.com/vpc-ext/compute/images
   * Alternatively, use the navigation menu to go to the Images for VPC page: ☰ > VPC Infrastructure > Images.
1. Select the version 1 `<your-username>-v1` image from the list of images.
1. From the **Actions** menu, choose **Schedule lifecycle**.
1. Set **Image status** to **Set to obsolete**.
1. Select to apply the new status **Immediately**.
1. Click **Save**.
1. Go back to the list of images at https://cloud.ibm.com/vpc-ext/compute/images.
1. Notice your image is not marked as _Obsolete_ and can no longer be used to create new instances.

[⇨ Continue to Share in a private catalog](50-private-catalog.md)

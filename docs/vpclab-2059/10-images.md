# Images in IBM Cloud

When you provision IBM Cloud® Virtual Servers for Virtual Private Cloud, you can select from the supported virtual server operating system stock images, the virtual server operating system bundle stock image, or a custom image that you import from IBM Cloud Object Storage. The image that you select determines the operating system that is provisioned for your instance. If the image you select is a virtual server operating system bundle stock image, the software that is part of that bundle is also included in your instance.

You find 3 categories of images in IBM Cloud:
* Stock images
* Custom images
* Catalog images

## Log in to IBM Cloud

1. Go to https://ibm.biz/vpc-labs-invite.
1. Enter the `Username` and `Password` provided for the lab.
1. Click **Sign in**.
  ![](images/10-login.png ':size=600')
1. You must provide a trusted profile. **Select** the trusted profile tile labeled **Attendee for IBM TechXchange 2023**
  ![](images/10-select-profile.png ':size=400')

## Stock images

When you provision a virtual server on your VPC, you need to select an image to determine the operating system for the server. The following are the virtual server operating system stock images available when you create a virtual server:
* x86 virtual server images
* s390x virtual server images
* Bare metal server images
* s390x bare metal server images

1. To view existing stock images, go to https://cloud.ibm.com/vpc-ext/compute/images.
   * Alternatively, use the navigation menu to go to the Images for VPC page: ☰ > VPC Infrastructure > Images.
1. Select the **Stock images** tab.
   ![](images/10-stock-images.png ':size=400')

## Custom images

Custom images are used to create new virtual servers with your own settings and configurations. You can create a Linux® custom image, a Windows® custom image, a z/OS Wazi aaS custom image, or a VMware custom image. You can import your custom image directly into IBM Cloud® Virtual Private Cloud from IBM Cloud® Object Storage or create one from an existing virtual server boot volume.

All images in IBM Cloud are **cloud-init** enabled. cloud-init is a software package that automates the initialization of cloud instances during system boot. Most open source Linux distributions produce a cloud-init enabled image in the `qcow2` format. These files can be used without modification in IBM Cloud.

In this lab, a Linux (Debian 10) image file has been preloaded in a Cloud Object Storage bucket. It was obtained from the Debian website (https://cloud.debian.org/images/cloud/buster/20201214-484/). You will use it to create a custom image.
   ![](images/website-image.png ':size=400')

The part in yellow in the diagram below has already been completed:
  ![](images/upload-image.svg ':size=400')

To confirm the image file has been correctly preloaded:
1. Go to the Resource List at https://cloud.ibm.com/resources.
   * Alternatively, use the navigation menu to go to the Resource list page: ☰ > Resource list.
1. Expand the **Storage** category.
1. Click on the **vpc-labs-2059-cos** service.
1. Click on the **vpc-labs-2059-upload** bucket.
1. Look for the **deb10.qcow2** in the **Objects** table.
   ![](images/10-deb-10.png ':size=400')

## Catalog images

If you plan to share or publish a custom image to other accounts within your enterprise, you need to create a private catalog. A private catalog provides a way for you to manage access to products for multiple accounts while those accounts are within the same enterprise. You can share any existing virtual server custom image with a private catalog, except for an encrypted image.

This lab includes an optional section to do this.

[⇨ Continue to Import a third party image](15-import-third-party-image.md)

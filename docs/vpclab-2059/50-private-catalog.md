# Create private catalog product version

The images you created are available to other users within your account - provided that they have the proper permissions configured.

If you plan to share or publish a custom image to other accounts within your enterprise, you need to create a **private catalog**. A private catalog provides a way for you to manage access to products for multiple accounts while those accounts are within the same enterprise. You can share any existing virtual server custom image with a private catalog, except for an encrypted image.

Private catalogs are ideal for distributing hardened corporate images across an enterprise.

There is a private catalog product type specifically for VPC custom images. A single catalog product version captures identical images from multiple regions. When a VPC virtual server instance is provisioned from a catalog product version, the appropriate regional image will be used. The IBM Cloud console, Terraform, Packer and CLI accept catalog product versions when creating VSIs.

In this step a catalog product version will be created (shown in yellow):
   ![](images/catalog.svg ':size=600')

## Create a private catalog

1. Go to https://cloud.ibm.com/content-mgmt/overview to create a catalog
   * Alternatively, use the top menu to go to **Manage** > **Catalogs**.
   ![](images/50-manage-catalog.png ':size=400')
1. Click **Create a catalog**.
   1. Set **Catalog type** to **Product (default)**.
   1. Set **Name** to `<your-username>-catalog`. As example `vpclab-123-catalog`.
   1. Keep the default resource group.
   1. Select the **template** named **No products**.
1. Click **Create**.

## Add product to the private catalog

To add the custom image to the catalog:
1. Click **Add**.
1. Set **Product type** to **Software**.
1. Set **Delivery method** to **Virtual server image for VPC**.
   ![](images/50-product.png ':size=400')
1. Set **Architecture** to **x86**.
1. Set **Region** to **Dallas (us-south)**.
1. Under **Available images**, select your image `<your-username>-v2`. As example `vpclab-123-v2`.
1. Set **Software version** to **2.0.0**.
1. Set **Category** to **Compute / Virtual Machines**.
1. Click **Add product**.
   ![](images/50-add-product.png ':size=400')

## Rename the product

The product is created with the name of the image which includes the version. Let's rename it:
1. Click the **Edit** pencil to modify the Catalog entry details.
1. Set **Product name** and **Programmatic name** to `<your-username>`. As example `vpclab-123`.
1. Click **Save**

## Validate the product version

Before it can be shared, the product version needs to be validated. In the **Version list** of the catalog product, notice there is a version *2.0.0* in the *Draft* state.

 You will skip over some of the fields in the configuration in this introduction.

### Configure version

1. From the **Version list**, click the version **2.0.0** just created.
   * You may get an error message referring to `BSS Licenses`, simply dismiss the dialog.
1. In the **Configure version** section:
   1. In **Review regions** notice the image added earlier and click **Next**.
   1. In **Review the version details** there is an opportunity to add more details like the URL to the release notes. Click **Next**.

### Add license agreements

1. In the **Add license agreements** section, you can any license agreement you want to show users when they use your product. Skip for now and click **Next**.

### Edit readme

1. In the **Edit readme** section, you can provide a description of your product. Skip for now and click **Next**.

### Validate version

In the **Validate version** section, a virtual server instance is going to be provisioned with your custom image to confirm it is working properly.
1. Configure the validation target:
   1. Set **Virtual Private Cloud** to **vpc-labs-2059-vpc**.
   1. Set **SSH key** to `<your-username>-key`. As example `vpclab-123-key`.
   1. Set **Subnet** to **us-south-2**.
   1. Set **Profile** to **cx2-2x4**.
   1. Click **Next**.
1. Configure Schematics workspace:
   1. Keep the default name.
   1. Keep the default resource group.
   1. Set **Schematics region** to **Dallas (us-south)**.
   1. Click **Next**.
1. Validate version:
   1. Click **Validate**. This is going to create a *Schematics* workspace and create an instance with the image provided to the catalog product version.  Wait for a few minutes to make it through the phases of:
      1. Submit deployment.
      1. Prepare installation.
      1. Install product.
   1. Click **Next**.

### Manage compliance

1. Manage compliance allows compliance controls to be added to the product.  Skip for now and click **Next**.

### Review requirements

1. In **Review requirements**, click **Ready to share**.
1. Confirm *Ready to share*.
1. Click each of the boxes for **Version status**, **Version details** and **Image details** to see more information.

## Confirm the image is available as a catalog product

1. Go to https://cloud.ibm.com/vpc-ext/compute/vs.
   * Alternatively, use the navigation menu to go to the Virtual server instances page: ☰ > VPC Infrastructure > Virtual server instances.
1. Click **Create**.
1. Scroll to **Image and profile**, click **Change image**.
1. Select the **Catalog images** tab at the top.
1. Find your custom image in the list `<your-username>`. As example `vpclab-123`.
   ![](images/50-image-in-catalog.png ':size=500')

In this section, you shared a custom image in a private catalog and made it available to provision new virtual server instances.

[⇨ Continue to Distribute across regions](70-image-export-import.md)

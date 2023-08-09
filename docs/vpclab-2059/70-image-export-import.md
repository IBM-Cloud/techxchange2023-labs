# Distribute across regions

In this section, you will make your custom image available to another IBM Cloud region. The part in yellow in this diagram will be completed:
   ![](images/multi-region.svg ':size=600')

To make an image available to another region, you first export it to a Cloud Object Storage bucket and then import it into the Image service for the target region.

## Export image to a bucket

1. Go to https://cloud.ibm.com/vpc-ext/compute/images
   * Alternatively, use the navigation menu to go to the Images for VPC page: ☰ > VPC Infrastructure > Images.
1. Click on your image `<your-username>-v2`. As example `vpclab-123-v2`.
1. From the **Actions** menu, choose **Export**.
1. Set **Export file format** to **QCOW2**.
1. Set **Cloud Object Storage instance** to **vpc-labs-2059-cos**.
   * You can ignore the warning about IAM authorization.
1. Set **Location** to **us-south**.
1. Set **Bucket** to **vpc-labs-2059-export-import**.
   ![](images/70-export-image.png ':size=400')
1. Select the **Export history** tab to monitor the progress and wait for the job to be **Completed**.
   ![](images/70-export-completed.png ':size=400')

## Import image to another region.

1. Go to https://cloud.ibm.com/vpc-ext/compute/images
   * Alternatively, use the navigation menu to go to the Images for VPC page: ☰ > VPC Infrastructure > Images.
1. Select **Washington DC** as the target region.
1. Click **Create**.

Fill in the create image details:
1. Set **Geography** to **North America**.
1. Set **Region** to **Washington DC**.
1. Set **Name** to `<your-username>-v2`. As example `vpclab-123-v2`. It is best to use the same image name in both regions.  After all they are exactly the same image.
1. Keep the default value for **Resource group**.
1. Select **Cloud Object Storage** as **Image source**.
   1. Select the **vpc-labs-2059-cos** instance.
   1. Set the **Location** to **us-south**.
   1. Select the **vpc-labs-2059-export-import** bucket.
1. Select the image starting with your username. As example `vpclab-123-v2-vpclab-123-v2-breeze-johnniecake-unworldly-smugness.qcow2`.
1. Set the **Operating System** to **Debian GNU/Linux**.
1. Set the **Version** to **debian-10-amd64**.
1. Review the settings and click **Create custom image**.
   ![](images/70-create-custom-image.png ':size=600')
1. The custom image is added to the list. Wait for the custom image creation to be marked as **Available**.

## Add the new image to the catalog product version

1. Go to https://cloud.ibm.com/content-mgmt/overview to find the catalog you created in the previous section
   * Alternatively, use the top menu to go to **Manage** > **Catalogs**.
   ![](images/50-manage-catalog.png ':size=400')
1. Select the **Private catalogs** tab on the left.
1. Select the catalog named after your username. As example `vpclab-123-catalog`.
1. Click on the product `<your-username>`.
1. In the **Version list**, click on the version you created earlier, **2.0.0**.
1. Click **Edit version** at the top right.
1. In **Review regions** table, click **Add region**.
1. Select the image that you just created in the other region.
1. Click **Add region**.
1. Select **Review requirements** in the left list of steps.
1. Click **Merge changes** and confirm the **Merge**.
   ![](images/70-merge-changes.png ':size=500')

You have added an additional region to the catalog entry. Your custom image is now available for provisioning in two different regions.

[⇨ Continue to Conclusion](75-conclusion.md)

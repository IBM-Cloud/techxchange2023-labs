# Conclusion

You have been through the mechanics of creating VPC images.

They must be [cloud-init](https://cloudinit.readthedocs.io/en/latest/) multi-distribution images. [Getting started with Stock images on VPC](https://cloud.ibm.com/docs/vpc?topic=vpc-getting-started-images-on-vpc-stock) is the easiest way to go.

You can also upload and import them from the providers of operating systems. Most provide `qcow2` cloud-init images that are ready to use. You can bring custom images that you are using on premises as well. [Getting started with custom images](https://cloud.ibm.com/docs/vpc?topic=vpc-planning-custom-images) describes in more detail importing your own images.

Over time you will find that old images need to be deprecated and made obsolete. Use the [custom image lifecycle](https://cloud.ibm.com/docs/vpc?topic=vpc-planning-custom-images&interface=ui#custom-image-lifecycle) for image life cycle management over time.

To distribute images across your organization, create a private catalog and then a VPC Image product.  Add identical images in each region that you support. Catalog products can be shared across accounts in an enterprise.

Most corporations have corporate compliance requirements that are continuously adapting to security concerns and general software currency.
  * Simplify the creation of images that meet your corporate compliance requirements images meeting the latest corporate compliance using a [Continuous Delivery](https://www.ibm.com/cloud/continuous-delivery).
  * IBM VPC Images can be created using a command line tool like [Packer](https://www.packer.io/). See [Build Hardened and Pre-Configured VPC Custom Images with Packer](https://www.ibm.com/cloud/blog/build-hardened-and-pre-configured-vpc-custom-images-with-packer) for a complete example.

## (Optional) Cleanup 🧹

### Delete instances

1. Go to https://cloud.ibm.com/vpc-ext/compute/vs
1. Select **Dallas** as the target region.
1. Find the virtual server instances you created.
   ![](images/75-delete-vsi.png ':size=500')
1. Use the action menu ⁝ on the right of the table to **Delete** the instance.

### Delete Schematics workspace

1. Go to https://cloud.ibm.com/schematics/workspaces
1. Search for an entry named after your username.
1. Click on the entry.
1. From the **Actions** menu, select **Destroy resources**.
1. Follow confirmation instructions.
1. From the **Actions** menu, select **Delete workspace**.
1. Follow confirmation instructions.

<!--
## Delete SSH Key
## Delete catalog
### Delete products then delete catalog
## Delete custom images
-->

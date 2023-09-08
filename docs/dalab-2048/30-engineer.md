# Deploy an architecture as Engineer

As Engineer, your role includes providing other teams with ready-to-use environments to build applications. In this section, you will:
* import a sample product in a private catalog,
* and deploy an instance of this product.

## Log in as Compliance Manager

1. Log out from the IBM Cloud console.
1. Go to https://ibm.biz/lab2048-invite.
1. Enter the `Username` and `Password` provided for the lab.
1. Click **Sign in**.
1. **Select** the trusted profile tile labeled **Engineer**.
1. You should now be successfully logged in as an **Engineer** on the **IBM Cloud console**.

## Create a new product in a private catalog

1. Go to the *Private Catalogs* list at https://cloud.ibm.com/content-mgmt/catalogs.
   * Alternatively, use the top right menu to go to the _Private Catalogs_ page: Manage > Catalogs.
1. Select the existing **Catalog for engineers** from the list.
1. Click **Add** to create a new product.
1. Set **Product type** to **Deployable architecture**.
1. Set **Delivery method** to **Terraform**.
1. Set **Repository type** to **Public repository**.
1. Set **Source URL** to `https://github.com/l2fprod/techxchange-simple-da/archive/refs/tags/v1.1.0.tar.gz`.
1. Set **Variation** to **Standard**.
1. Click **Add product**.
  ![](images/30-add-product.png ':size=400')

## Rename the product

1. Click **Edit** to modify the **Catalog entry details**.
1. Edit the **Product name** and add `<your-username> - ` as a prefix to make it unique. As example `dalab-123 - Simple deployable architecture`.
1. Click **Save**.

## Validate the product

1. In the **Version list**, click the first (and only) version.
   * You may get an error message referring to `BSS Licenses`, simply dismiss the dialog.
1. Most values in the wizard have been prefilled when you imported the product from the Source URL.
1. **Configure version** includes version details, deployment values such as input variables and the list of permissions required to deploy the product.
1. Click **Next** until you reach the **Add deployable architecture details** step.
1. **Add deployable architecture details** allows to provide architecture diagrams, prerequisites and highlights for the product.
1. Click **Next** until you reach the **Add license agreements** step.
1. **Add license agreements** specifies the licenses that the end-user should accept when deploying the product.
1. Click **Next**.
1. **Edit readme** documents the product.
1. **Click Next**.

This **Validate version** step verifies that the product can be deployed by performing a test deployment in your account.

1. In **Step 1 - Configure Schematics workspace**, set **Resource group** to the resource name matching your username, as example `dalab-123`.
  ![](images/30-set-resource-group.png ':size=400')
1. In **Step 2 - Input variables**, set **username** to `<your-username>`, as example `dalab-123`. This will make sure the resources are created in _your_ resource group. The resource group you configured earlier as Compliance Manager in the Security and Compliance attachment.
  ![](images/30-set-input-variable.png ':size=400')
1. In **Step 3 - Validate version**, check the license agreement.
1. Click **Validate**.
1. Wait for the validation to complete.
1. Once _Validated_, click **Next**.
  ![](images/30-validated.png ':size=400')
1. **Review Cost** gives an estimate of the cost of the deployed resources.
1. **Click Next**.
1. **Manage compliance** allows to specify which compliance controls are claimed by the product. This sample product specifies one.
1. Skip the scan by clicking **Next**.
1. You are ready to make the product available in the private catalog. Click **Ready to share**.
  ![](images/30-ready-to-share.png ':size=400')

?> All the predefined values in the wizard are defined in the file [`ibm_catalog.json`](https://github.com/l2fprod/techxchange-simple-da/blob/main/ibm_catalog.json) packaged with the Source URL you specified.

## Deploy the product

Now that the product is available, you can deploy a first version using _Projects_. *Projects* are a named collection of configurations that are used to manage related resources and Infrastructure as Code (IaC) deployments. A _deployable architecture_ is a cloud automation for deploying a common architectural pattern that combines one or more cloud resources that are designed for easy deployment, scalability and modularity. The product you just created is a deployable architecture.

### Deploy from catalog

1. Go to the IBM Cloud catalog https://cloud.ibm.com/catalog.
1. Select the **Catalog for engineers** private catalog.
  ![](images/30-select-catalog.png ':size=400')
1. Locate the tile for your product. It is named after your username. Notice the tile is marked as a _Deployable architecture_.
1. Click the tile.
1. In the product page, click **Review deployment options**.
  ![](images/30-product-tile-page.png ':size=400')
1. Click **Add to project**.

### Create a project

1. Select **Create new** in the **Add to project** panel.
1. Set **Name** to `<your-username>-project`, as example `dalab-123-project`.
1. Set **Resource group** to the resource name matching your username, as example `dalab-123`.
1. Click **Add**.

The project and project configuration get created.

### Specify parameters of the project configuration

1. In the **Configure** panel, in the **Security** tab, click **Select from Secrets Manager**.
   1. Set the **Service instance** to **da-lab-2048-secrets-manager**.
   1. Set the **Secret group** to **deployment**.
   1. Set the **Secret** to **api-key-for-deployment**.
   ![](images/30-project-set-api-key.png ':size=400')
1. In the **Required** tab, set the **username** parameter to `<your-username>`, as example `dalab-123`.
   ![](images/30-project-set-username.png ':size=400')
1. Click **Save** in the top right to persist the configuration.

### Validate and approve changes

Once saved, you can validate the project configuration before you can deploy the resources. This gives an opportunity to validate the changes that are about to be made.

1. Click **Validate** in the top right.
   ![](images/30-project-validation-starts.png ':size=400')
1. Wait for the validation to complete. When complete, it shows that the Security and compliance scan fails. This is expected as the sample does not include encryption.
   ![](images/30-project-validation-failed.png ':size=400')
1. Add a comment like **Force this deployment** and click **Override and approve**.
1. Click **Deploy**.
1. Eventually the deployment completes
   ![](images/30-project-deployed.png ':size=400')
1. Click **View resources**.
1. In the project configuration page, switch between **Resources** and **Outputs** to view the resources that were created.

You're done with the Engineer section. Notice that you deployed an architecture that is not fully compliant. Let's see how the Compliance Manager can audit the deployed resources and assess against the controls required by your organization.

⇨ [Continue with Assess the compliance as Compliance Manager](40-compliance.md)

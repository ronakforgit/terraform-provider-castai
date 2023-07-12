## Example for AKS with CAST AI Autoscaler policies and additional Node Configurations

The following example shows how to onboard an AKS cluster to CAST AI with custom app registration and role.

An example configuration should be analyzed in the following order:

1.  Create a Custom App registration and app role using `examples/aks/aks_cluster_custom_role/app-role` (change the variable names in locals )
2.  Create AKS cluster and onboard it to cast using `examples/aks/aks_cluster`

## Usage

1.  Rename `examples/aks/aks_cluster/tf.vars.example` to `examples/aks/aks_cluster/tf.vars`
2.  Update `examples/aks/aks_cluster/tf.vars` file with your cluster name, cluster region and CAST AI API token.
3.  Update variables `role_name` and `app_name` in  `examples/aks/aks_cluster_custom_role/app-role/iam-deployment.tf`
4.  Execute the respective terraform project first `app_role` and then `aks_cluster`


Here are the steps to executing the demonstration:

**Creation of the application registration and role:**  
1\. Go to the **"app-role"** directory and initialize the Terraform repository: `terraform init`  
2\. Apply the Terraform configuration: `terraform apply -var="cluster_name=my-cluster" -var="subscription_id=your_subscription_id"`

**Creation of the AKS cluster and its integration with Cast.ai:**  
1\. Go to the **"aks\_cluster"** directory and initialize the Terraform repository: `terraform init`  
2\. Edit the "`tf.vars`" file and use the same cluster name that was used when creating the application registration and role.  
3\. Review the Terraform plan: `terraform plan –var-file=tf.vars`  
4\. Apply the Terraform configuration: `terraform apply –var-file=tf.vars`

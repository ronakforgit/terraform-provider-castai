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

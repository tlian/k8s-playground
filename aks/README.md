# Azure Kubernetes Service via Terraform

This module will quickly spin up a simple AKS cluster.
The only required variables are
 - ResourceGroup name
 - AKS Cluster name
Provide any arbitrary values for the above variables.
All other variables were set to some default values which all can be changed to any arbitrary value.

## Pre-requisite
 - Install Azure CLI

   On MacOs:  ```brew install azure-cli```
 - Install kubectl

   On MacOs: ```brew install kubectl```

### Example
```
git clone git@github.com:openrba/aks-playground.git
cd k8s-datadog-monitoring/aks
az login
terraform init
terraform plan
terraform apply -auto-approve
```
Once Terraform applied successfully, there will be an output which is required to set up authentication with the newly spinned up AKS cluster.
The output will look something like
```
az aks get-credentials --name <NAME-OF-AKS-CLUSTER> --resource-group <NAME-OF-RESOURCE-GROUP>
```
Run the above command once and it should all set up.
> Warning: Make sure ~/.kube/config file exist. If not, do ```touch ~/.kube/config```

To verify 
```
kubectl get namespaces
```

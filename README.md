# azure-arc-imaging-ingestion

## Pre-requisites

* Azure Arc enabled kubernetes cluster: https://azurearcjumpstart.io/azure_arc_jumpstart/azure_arc_k8s/

## Deployment

* Get Cluster Name and Resource Group

```
az connectedk8s list -o table
```

* Create gitOps configuration

```
az k8s-configuration create --name alvearie-imaging-ingestion --cluster-name <ClusterName> --resource-group <ResourceGroup> --operator-instance-name cluster-config --operator-namespace cluster-config --repository-url https://github.com/jeesmon/azure-arc-imaging-ingestion --scope cluster --cluster-type connectedClusters --operator-params "--git-readonly --git-branch=main"
```

More details: https://docs.microsoft.com/en-us/azure/azure-arc/kubernetes/tutorial-use-gitops-connected-cluster

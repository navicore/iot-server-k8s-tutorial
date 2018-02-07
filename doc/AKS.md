### AKS Kubernetes

```console
az login
```

```console
az account show
```

if the above command does not show your subscription in the "ID" field, ie: the one you intend to use, set it via
```console
az account set --subscription YOUR_SUBSCRIPTION_ID
```

pick a unique value for YOUR_CLUSTER like maryjane-aks1.  you will reference YOUR_CLUSTER name in other commands below.  I use the same name for both cluster and resource group.

```console
az group create -n YOUR_CLUSTER -l eastus
```

point to a public ssh key - it is fine to use your default one since this is your personal cluster
```console
az aks create -n YOUR_CLUSTER -g YOUR_CLUSTER --admin-username localadmin --ssh-key-value ~/.ssh/id_rsa.pub --node-vm-size Standard_D2_v2 --node-count 2 --kubernetes-version 1.8.2
```

```console
az aks get-credentials -n YOUR_CLUSTER -g YOUR_CLUSTER
```

look at the contents of ~/.kube/config

```console
kubectl get nodes
```

```console
kubectl get pods
```

```console
kubectl -n kube-system get pods
```

```console
az aks scale -n iottut -g iottut --node-count 3
```

get k8s ui
```console
kubectl proxy
```
use browser with http://localhost:8001/ui



### AKS Kubernetes

```console
az account show
```

```console
az group create -n YOUR_CLUSTER -l eastus
```

pick a unique name for YOUR_CLUSTER and YOUR_USERID and make sure you have a public ssh key handy
```console
az aks create -n YOUR_CLUSTER -g YOUR_CLUSTER --admin-username YOUR_USERID --ssh-key-value ~/.ssh/id_rsa.pub --node-vm-size Standard_D2_v2 --node-count 2 --kubernetes-version 1.8.2
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



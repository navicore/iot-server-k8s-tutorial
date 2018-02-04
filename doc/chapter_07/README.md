Istio with Cassandra
---

### Goals: understand how to install an envoy (istio) sidecar with your pods

```console
kubectl create -f ./storageclass.yaml
```

```console
kubectl create -f ./service.yaml
```

create deployment with istio sidecar

```console
kubectl apply -f <(istioctl kube-inject -f ./deployment.yaml)
```

```console
kubectl exec -it my-cassandra-CHANGEME-CHANCEME bash
```

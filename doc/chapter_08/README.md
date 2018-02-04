istio with Kafka
---

### Goals: reinforce understanding of installing an envoy (istio) sidecar with your pods

```console
kubectl create -f ./service.yaml
```

create deployment with istio sidecar

```console
kubectl apply -f <(istioctl kube-inject -f ./deployment.yaml)
```


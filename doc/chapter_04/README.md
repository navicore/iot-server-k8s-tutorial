deploy iot-server-demo (single pod)
---

### Goals: understand how pods communicate with each other via services

```console
kubectl create -f ./service.yaml
```

```console
kubectl get service
```

```console
kubectl create -f ./deployment.yaml
```

```console
kubectl get pod
```

```console
kubectl port-forward iot-server-demo-CHANGEME-CHANGEME 8080:8080
```

use a rest client or curl to send posts to app (see get.rest)

cleanup

```console
kubectl delete -f ./service.yaml
kubectl delete -f ./deployment.yaml
```


kubectl run
---

### Goals: understand how to create a pod, query system for pod status, and test

The [run](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#run) command automatically creates a deployment

```console
kubectl run --image=nginx nginx-app --port=80 --env="DOMAIN=cluster"
```

```console
kubectl get deployment
```

```console
kubectl get pods
```

```console
kubectl port-forward nginx-app-CHANGEME-CHANGEME 8080:80
```

use your browser to see http://localhost:8080

CNTR-C to end port forwarding

```console
kubectl delete pod nginx-app-CHANGEME-CHANGEME
```

see a new pod get automatically created by the deployment

```console
kubectl get pods
```

Use `kubectl` [scale](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#scale) command`
```console
kubectl  scale deployment --replicas 2 nginx-app
```

```console
kubectl get pods -o wide
```

```console
kubectl scale deployment --replicas 100 nginx-app
```

```console
kubectl get pods
```

```console
kubectl edit deployment nginx-app
```

change replicas to 10 and save `:wq`

see the pod count get automatically updated by the deployment

```console
kubectl get pods
```

```console
kubectl delete deployment nginx-app
```


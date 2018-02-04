Deploy iot-server-demo (statefulset)
---

### Goals: understand how to create statefulsets

See helpful [Software Mill blog post] for inspiration.

Components:

 * service for seeds StatefulSet
 * service for http ingress
 * ingress controller
 * StatefulSet for seeds
 * Deployment for kafka ingestion stream
 * Deployment for workers that also serve as http handlers for ingress service

[Software Mill blog post]: https://medium.com/google-cloud/clustering-akka-in-kubernetes-with-statefulset-and-deployment-459c0e05f2ea

```console
kubectl create -f ./service.yaml
```

```console
kubectl get service
```

Create [stateful set](https://kubernetes.io/docs/tutorials/stateful-application/basic-stateful-set/)
```console
kubectl create -f ./seed.yaml
```

```console
kubectl get pods
```

```console
kubectl scale statefulset --replicas 3 iot-server-demo-seed
```

notice the pod names are predictable (iot-server-demo-seed-0, iot-server-demo-seed-1)

```console
kubectl create -f ./streamer.yaml
```

cleanup

```console
kubectl delete deployment iot-server-demo-streamer my-cassandra streamer my-kafka
kubectl delete statefulset iot-server-demo-seed
kubectl delete service iot-server-demo-seed my-kafka my-cassandra
```

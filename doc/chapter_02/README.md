Deploy Cassandra
---

### Goals: understand how to create a deployment that uses storage

Create the [storage class](https://kubernetes.io/docs/concepts/storage/storage-classes/)
```console
kubectl create -f ./storageclass.yaml
```

Create the [service](https://kubernetes.io/docs/concepts/services-networking/service/)
```console
kubectl create -f ./service.yaml
```

```console
kubectl get service
```

Create the [deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) and [persistent volume claim](https://kubernetes.io/docs/concepts/storage/persistent-volumes/) 

note, look in the yaml file and see two definitions in the single file
```console
kubectl create -f ./deployment.yaml
```

```console
kubectl describe persistentvolumeclaim
```

```console
kubectl get pod
```

```console
kubectl describe pod my-cassandra-CHANGEME-CHANGEME
```

```console
kubectl logs -f my-cassandra-fc6db57c6-8hcmd
```

```console
kubectl exec -it my-cassandra-CHANGEME-CHANGEME bash
```

do some cqlsh stuff (create a keyspace)

delete the pod and when a new one is created, make sure your stuff is there.


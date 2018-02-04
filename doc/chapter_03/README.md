Deploy Kafka
---

### Goals: reinforce understanding of how to create a deployment

```console
kubectl create -f ./storageclass.yaml
```

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
kubectl describe pod my-kafka-CHANGEME-CHANGEME
```

```console
kubectl logs -f my-kafka-CHANGEME-CHANGEME
```

```console
kubectl exec -it my-kafka-CHANGEME-CHANGEME bash
```

cd into bin and do some kafka stuff, create a topic

```console
./kafka-topics.sh --create --topic mytopic --zookeeper localhost --partitions 2 --replication-factor 1
```


istio with iot-server-demo (single deployment)
---

### Goals: use istio to open a tls ingress end-to-end public IP

```console
kubectl create -f ./service.yaml
```

create deployment with istio sidecar
```console
kubectl apply -f <(istioctl kube-inject -f ./deployment.yaml)
```

create self-signed cert for ingress and store as k8s [secret](https://kubernetes.io/docs/concepts/configuration/secret/)
```console
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /tmp/tls.key -out /tmp/tls.crt -subj "/CN=my.domain.com"
kubectl create -n istio-system secret tls istio-ingress-certs --key /tmp/tls.key --cert /tmp/tls.crt
```

create [ingress](https://kubernetes.io/docs/concepts/services-networking/ingress/) - open to the internet w/ SSL
```console
kubectl create -f ./kubectl-ingress.yaml
```

```console
kubectl get ingress
```

watch for public IP to get created after a couple minutes...


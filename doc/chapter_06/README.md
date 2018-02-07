Istio with tls and metrics
---

### Goals: understand how to install istio

See https://istio.io/

```console
curl -L https://git.io/getLatestIstio | sh -
cd istio-0.5.0/
export PATH=~./bin:$PATH
```

```console
istioctl -h
```

install istio into your cluster

```console
kubectl apply -f install/kubernetes/istio.yaml
```

```console
kubectl -n istio-system get pods
```

install zipkin and prometheus and grafana
```console
kubectl apply -f install/kubernetes/addons/zipkin.yaml
kubectl apply -f install/kubernetes/addons/prometheus.yaml
kubectl apply -f install/kubernetes/addons/grafana.yaml
```

access zipkin dash
```console
kubectl port-forward -n istio-system $(kubectl get pod -n istio-system -l app=zipkin -o jsonpath='{.items[0].metadata.name}') 9411:9411 &
```
open with browser http://localhost:9411


access prometheus dash
```console
kubectl port-forward -n istio-system $(kubectl get pod -n istio-system -l app=zipkin -o jsonpath='{.items[0].metadata.name}') 9411:9411 &
```
open with browser http://localhost:9090


access grafana dash
```console
kubectl -n istio-system port-forward $(kubectl -n istio-system get pod -l app=grafana -o jsonpath='{.items[0].metadata.name}') 3000:3000 &
```
open with browser http://localhost:3000


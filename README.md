IOT Server K8S Tutorial
---

Some notes I use when introducint Kubernetes.  Experimental,
unproven.  Use at your own risk.

The Cassandra and Kafka setups here are toy deployments - don't use for real work.

Best ways to learn Kubernetes are:
 1. Joe Beda's [TGI Kubernetes](https://www.youtube.com/results?search_query=tgi+kubernetes)
 2. Kelsey Hightower's [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way) or an [Azure fork](https://github.com/ivanfioravanti/kubernetes-the-hard-way-on-azure)
 3. Kubernetes [documentation](https://kubernetes.io/docs/home/)

### [Background Talk](doc/BACKGROUND.md)

### [Kubernetes Talk](doc/K8S.md)

Prerequisites: 
  * clone of this repo
  * installed `kubectl`
  * any Kubernetes cluster >= 1.8.x (see K8S.md for instructions for creating a cluster on Azure)

### [Chapter 0 Begin Lab!](doc/AKS.md) - setup aks

### [Chapter 1](doc/chapter_01/README.md) - kubectl run

### [Chapter 2](doc/chapter_02/README.md) - deploy Cassandra

### [Chapter 3](doc/chapter_03/README.md) - deploy Kafka

### [Chapter 4](doc/chapter_04/README.md) - deploy iot-server-demo (single pod)

### [Chapter 5](doc/chapter_05/README.md) - deploy iot-server-demo (statefulset)

### [Chapter 6](doc/chapter_06/README.md) - istio with tls and metrics

### [Chapter 7](doc/chapter_07/README.md) - istio with Cassandra

### [Chapter 8](doc/chapter_08/README.md) - istio with Kafka

### [Chapter 9](doc/chapter_09/README.md) - istio with iot-server-demo (single deployment)

---

More:

* Setup [tab completion](https://kubernetes.io/docs/tasks/tools/install-kubectl/#enabling-shell-autocompletion) for `kubectl`
* RBAC
* SSO
* Azure Container Registry via K8S Secrets
* ConfigMap
* run Jenkins on K8S
* Ingress without istio
* use helm to install Kafka and other well-known packages
* use DaemonSet with fluentd to forward logs to splunk
* Integrate Kubernetes Secrets with Vault (or other)
* Get deeper into the future of container mgmt experiment with [Cilium](http://docs.cilium.io/en/latest/gettingstarted/istio/)

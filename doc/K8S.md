IOT Server K8S Tutorial Kubernetes Talk
---

### Kubernetes

  (20 minutes)

  * POD
    1. building block
    2. contains 1 or more co-located containers
    3. every container in a pod shares a pid and net namespace
  * Service
    1. IP address discovery for pods with appropriate labels
    2. abstracts pod2pod routing rules
  * Deployment
    1. replication set
    2. scaling
    3. works in concert with service for lb
  * StatefulSet
    1. replication set
    2. pods2pod uses unique name per pod
    3. startup of pods in sequetial order (slow)
  * PersistenceClaim
  * Ingress


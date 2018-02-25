
# Prerequisites

Kubernetes Cluster

Kubectl installed and configured

Tiller server and Helm cli (Optional)

A stoarge class must exist. You d'ont need to setup a new storage class with AKS.


# RUN Rabbitmq HA with Kube tempales


[Secret](https://github.com/aliouba/rabbitmq-ha-kubernetes/blob/master/secret.yaml) : Define rabbitmq erlang cookie and rabbitmq password

[Config Map](https://github.com/aliouba/rabbitmq-ha-kubernetes/blob/master/cm.yaml) : Customize rabbitmq cluster configuration 

[Servive](https://github.com/aliouba/rabbitmq-ha-kubernetes/blob/master/svc.yaml) : this service is only accessible through the Kube cluster. It exposes 15672, 5672 and 4369 ports.

[Statefulset](https://github.com/aliouba/rabbitmq-ha-kubernetes/blob/master/statefulset.yaml). It launches 3 rabbitmq instances (cluster mode). Use this file template to choose your disk size for rabbitmq data persistence. A PVC will be created for each rabbitmq instance.


# RUN Rabbitmq with Helm (Recommended)

Don't forget to disable RBAC if you use the official helm chart to run rabbitmq on AKS. At the moment RBAC functionality is not available on AKS.

helm install --name myrelease stable/rabbitmq-ha --set rbac.create=false


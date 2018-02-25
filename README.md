
# Prerequisites

Kubernetes Cluster

Kubectl installed and configured

Tiller server and Helm cli (Optional)

A stoarge class must exist. You d'ont need to setup a new storage class with AKS.


# RUN Rabbitmq HA with Kube tempales



# RUN Rabbitmq with Helm

Don't forget to disable RBAC if you use the official helm chart to run rabbitmq on AKS. At the moment RBAC functionality is not available on AKS.

helm install --name myrelease stable/rabbitmq-ha --set rbac.create=false


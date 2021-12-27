## What is container orchestration
Container orchestration is the automation of operational effort required to run containerized workloads and services. 
This includes provisioning, deployment, scaling (up and down), networking, load balancing and more.

## What is k8s
K8s is a container orchestration tool.

## what is K8s architecture

## Whats are k8s cluster components
K8s cluster will have two main components
1. control plane (Master node)
   - **Kube-API server**: Users, the different parts of your cluster, and external components all communicate with one another through the API server.
   - **ETCD**: cluster’s database
   - **Kube-scheduler**: watches for newly created Pods with no assigned node, and selects a node for them to run on.But it doesn’t do the work of actually launching Pods on Nodes.
   - **Kube-control-manager:** Whenever the current state of the cluster doesn’t match the desired state, kube-controller-manager will attempt to make changes to achieve the desired state.
   - **Kube-cloud-control-manager:** kube-cloud-manager manages controllers that interact with underlying cloud providers.
2. worker Node 
   - **kubelet:** An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod. 
   - **kube-proxy:** kube-proxy is a network proxy that runs on each node in your cluster

> Container runtime is pre req for k8s.

## whick k8s component creates the POD
kubelet

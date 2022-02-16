## What is container orchestration
Container orchestration is the automation of operational effort required to run containerized workloads and services. 
This includes provisioning, deployment, scaling (up and down), networking, load balancing and more.

## What is k8s
K8s is a container orchestration tool.

## what is K8s architecture
https://github.com/bhaaskara/Kubernetes/blob/main/K8s_concepts.md#k8s-architecture

## What are k8s cluster components
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

> Container runtime (like docker) is pre req for k8s.

## whick k8s component creates the POD
kubelet

## how to identify the backend pods of a service
## How to dry run the k8s commands
## how to verify the syntax of the k8s deployment yaml file

# Deployment Use Cases in Kubernetes
**Use Case 1**- Create a Deployment: On the creation of deployment, Pods are created automatically by ReplicaSet in the background. 
**Use Case 2**- Update Deployment: Creation of new ReplicaSet happens and now the deployment is updated. Deployment revisions are updated through these new ReplicaSet. 
**Use Case 3**- Rollback Deployment: If the current deployment state is not steady, rollback of deployment happens. But we can see the container images are updated. 
**Use Case 4**- Scale a Deployment: Based on the requirement, scaling up or scaling down can be performed on each and every deployment. 
**Use Case 5**- Pause the Deployment: To apply various fixes, deployment can be paused and later resumed

# How to do maintenance activity on k8s node ?
Cordon the node - moves the node to maintenance mode
`kubectl cordon`
Drain the node -  discard the pod from the node
`kubectl drain –ignore-daemon set`

# How do we control the resource usage of POD?
With the use of limit and request resource usage of a POD can be controlled.

# What is PDB (Pod Disruption Budget)?
A Kubernetes administrator can create a deployment of a kind: PodDisruptionBudget for high availability of the application, it makes sure that the minimum number is running pods are respected as mentioned by the attribute minAvailable spec file. This is useful while performing a drain where the drain will halt until the PDB is respected to ensure the High Availability(HA) of the application. The following spec file also shows minAvailable as 2 which implies the minimum number of an available pod (even after the election).

Example: YAML Config using minAvailable

```yml
apiVersion: policy/v1beta1
kind: PodDisruptionBudget
metadata:
 name: zk-pdb
spec:
 minAvailable: 2
 selector:
   matchLabels:
     app: zookeepe
```

# What’s the init container and when it can be used?

# What is the role of Load Balance in K8s?

# What are the various things that can be done to increase k8s security ?
-   RBAC (Role-based access control) to narrow down the permissions.
-   Use namespaces to establish security boundaries.
-   Set the admission control policies to avoid running the privileged containers.
-   Turn on audit logging.

# How to monitor the Kubernetes cluster?
Prometheus is used for Kubernetes monitoring. The Prometheus ecosystem consists of multiple components.

-   Mainly Prometheus server which scrapes and stores time-series data.
-   Client libraries for instrumenting application code.
-   Push gateway for supporting short-lived jobs.
-   Special-purpose exporters for services like StatsD, HAProxy, Graphite, etc.
-   An alert manager to handle alerts on various support tools

### How to get the central logs from POD?
This architecture depends upon the application and many other factors. Following are the common logging patterns

-   Node level logging agent.
-   Streaming sidecar container.
-   Sidecar container with the logging agent.
-   Export logs directly from the application.
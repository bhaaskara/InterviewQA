# Basics
## What is container orchestration
Container orchestration is the automation of operational effort required to run containerized workloads and services. 
This includes provisioning, deployment, scaling (up or down), networking, load balancing and more.

![[Pasted image 20220305223242.png]]
## What is k8s
K8s is a container orchestration tool.
it's container management responsibilities include container deployment, scaling out and in, and also load balancing.

## K8s VS Docker swarm
![](Pasted%20image%2020220524141832.png)

## What is minikube?
Minikube is a tool that runs single node kubernetes cluster inside a VM, thus simplifying it for people to learn.

## What is federated cluster?
![](Pasted%20image%2020220524151426.png)

# Architecture
## What is K8s architecture
https://github.com/bhaaskara/Kubernetes/blob/main/K8s_concepts.md#k8s-architecture

## What are k8s cluster components
K8s cluster will have two main components
1. control plane (Master node)
   - **Kube-API server**: Users, the different parts of your cluster, and external components all communicate with one another through the API server.
      It validates and configures the data for API object such as PODs and services etc.
   - **ETCD**: cluster’s database
   - **Kube-scheduler**: watches for newly created Pods with no assigned node, and selects a node for them to run on. But it doesn’t do the work of actually launching Pods on Nodes.
   - **Kube-control-manager:** Whenever the current state of the cluster doesn’t match the desired state, kube-controller-manager will attempt to make changes to achieve the desired state.
     Controller manager is a daemon that embeds controllers.
     Different controllers are compiled into a single binary like node controller, replication controller, and endpoint controller.
   - **Kube-cloud-control-manager:** kube-cloud-manager manages controllers that interact with underlying cloud providers.
2. worker Node 
   - **kubelet:** An agent that runs on each node in the cluster. It makes sure that containers are running in a Pod. 
   - **kube-proxy:** kube-proxy is a network proxy that runs on each node in your cluster

> Container runtime (like docker) is pre req for k8s.

## What is kubectl?
Kubectl is the CLI interface for kubernetes cluster.

# RBAC
## What is kubeconfig file ?
The `kubectl` command-line tool uses kubeconfig files to connect with the cluster.

## What is context
Context binds users with the cluster and name space.
By setting the context we can define cluster, namespace and user to connect.
By default, the `kubectl` command-line tool uses parameters from the _current context_ to communicate with the cluster.

# How to schedule app pods on master node ?

# Pods
## Which k8s component creates the POD
kubelet

## Init containers
specialized containers that run before app containers in a [Pod](https://kubernetes.io/docs/concepts/workloads/pods/). Init containers can contain utilities or setup scripts not present in an app image.

## Live ness probes and ready ness probes

## Pending state
- when there are not enough resources
- when using host port
   - if you do require host port then you can only schedule as many pods as there are nodes.

## Reasons for crash loop back off error?
- application inside you container keeps crashing
- some type of parameters of POD/Container have been configured incorrectly
- an error has been made while deploying k8s.

## How to make sure a pod runs on a specific node ?
mentioning or using node selector label in POD.
using POD affinity

## how to check what are the activities performed by the container while creating the pod?
by checking the logs

## how to get IP of a POD?
`kubectl get pods -o wide`

## Job should be terminated after 40 secs
ActiveDeadLineSeconds: 40

## How do we control the resource usage of POD?
With the use of limit and request resource usage of a POD can be controlled.

# Resource limits
## can we set resource limits on each container?

# Service
## which network plugin your using
calico

## What are the different types of services?
Node port
Cluster IP
Load balancer

![](Pasted%20image%2020220524145205.png)


## What is headless service?
when you don't want load-balancing or a single cluster ip, you use headless service.
so you can directly reach pods with their DNS names.
it reduces coupling to Kubernetes system

## How to identify the backend pods of a service?
## How to dry run the k8s commands?
## How to verify the syntax of the k8s deployment yaml file

# Deployment Use Cases in Kubernetes
**Use Case 1**- Create a Deployment  
On the creation of deployment, Pods are created automatically by ReplicaSet in the background. 
**Use Case 2**- Update Deployment  
Creation of new ReplicaSet happens and now the deployment is updated. Deployment revisions are updated through these new ReplicaSet. 
**Use Case 3**- Rollback Deployment  
If the current deployment state is not steady, rollback of deployment happens. But we can see the container images are updated. 
**Use Case 4**- Scale a Deployment  
Based on the requirement, scaling up or scaling down can be performed on each and every deployment. 
**Use Case 5**- Pause the Deployment  
To apply various fixes, deployment can be paused and later resumed

# How to do maintenance activity on k8s node ?
Cordon the node - moves the node to maintenance mode
`kubectl cordon`
Drain the node -  discard the pod from the node
`kubectl drain –ignore-daemon set`

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
     app: zookeeper
```

# What is the role of Load Balance in K8s?

# What are the various things that can be done to increase k8s security ?
-   RBAC (Role-based access control) to narrow down the permissions.
-   Use namespaces to establish security boundaries.
-   Set the admission control policies to avoid running the privileged containers.
-   Restrict access to ETCD.
-   use images from authorized repositories only.
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

# Name space use cases ?
...

# What is an Operator?
Operators are software extensions to K8s which make use of custom resources to manage applications and their components. Operators follow Kubernetes principles, notably the control loop.

# Why do we need Operators?
The process of managing applications in Kubernetes isn't as straightforward as managing stateless applications, where reaching the desired status and upgrades are both handled the same way for every replica. In stateful applications, upgrading each replica might require different handling due to the stateful nature of the app, each replica might be in a different status. As a result, we often need a human operator to manage stateful applications. Kubernetes Operator is supposed to assist with this.

This will also help with automating a standard process on multiple Kubernetes clusters.

# What is Ingress Default Backend?
It specifies what to do with an incoming request to the Kubernetes cluster that isn't mapped to any backend i.e what to do when no rules being defined for the incoming HTTP request If the default backend service is not defined, it's recommended to define it so that users still see some kind of message instead of an unclear error.

# What is Kubernetes Load Balancing?
Load Balancing is one of the most common and standard ways of exposing the services. There are two types of load balancing in K8s and they are:

**Internal load balancer –** This type of balancer automatically balances loads and allocates the pods with the required incoming load.
**External Load Balancer –** This type of balancer directs the traffic from the external loads to backend pods

# How to troubleshoot if the POD is not getting scheduled?
In K8’s scheduler is responsible to spawn pods into nodes. There are many factors that can lead to unstart able POD. 
The most common one is running out of resources, use the commands like `kubectl describe <POD> -n <Namespace>` to see the reason why POD is not started. 
Also, keep an eye on `kubectl` to get events to see all events coming from the cluster.

# How to run a POD on a particular node?
   Various methods are available to achieve it.  
- nodeName specify the name of a node in POD spec configuration, it will try to run the POD on a specific node.  
- nodeSelector Assign a specific label to the node which has special resources and use the same label in POD spec so that POD will run only on that node.
- nodeaffinities required DuringSchedulingIgnoredDuringExecution, preferredDuringSchedulingIgnoredDuringExecution are hard and soft requirements for running the POD on specific nodes. This will be replacing nodeSelector in the future. It depends on the node labels.

# What are the different ways to provide external network connectivity to K8?
By default, POD should be able to reach the external network but vice-versa we need to make some changes. Following options are available to connect with POD from the outer world.

- Nodeport (it will expose one port on each node to communicate with it)
- Load balancers (L4 layer of TCP/IP protocol)
- Ingress (L7 layer of TCP/IP Protocol)

Another method is to use Kube-proxy which can expose a service with only cluster IP on the local system port.

# What are the security measures you can take while using k8s ?
- Apply security updates to environment regularly
- implement continuous security vulnerability scanning
- Restrict access to etcd
- Log everything on the prod environment.
- implement network segmentation
- define strict policies/rules for resources
- enable auditing
- provide limited access to k8s nodes
- define resource quotas
- use images from authorized repositories only

# Replicaset vs replication controller ?
Both of them uses different types of selectors to replicate the pods.
Replicaset uses set-based selectors while the replication controller use equity-based selectors.

# what is head less service

# What is heapster ?
A Heapster is a cluster wide aggregator of performance monitoring data collected by the Kubelet. This aggregator is natively supported and runs like any other pod within a Kubernetes cluster, which allows it to discover and query usage data from all nodes within the cluster.

# What is namespace?

# Default namespaces in k8s ?
- kube-system
- kube-public

# How can you get a static IP for a Kubernetes load balancer? 
A static IP for the Kubernetes load balancer can be achieved by changing DNS records since the Kubernetes Master can assign a new static IP address.

# Prometheus and Grafana
## What is promQL?
this is the query language used to query the prometheus.
used to create own queries and dash boards.

# What is taint and tolerance ?
**_Taints_** are applied to nodes, and allow a node to repel a set of pods.

**_Tolerations_** are applied to pods, and allow (but do not require) the pods to schedule onto nodes with matching taints.

Taints and tolerations work together to ensure that pods are not scheduled onto inappropriate nodes. One or more taints are applied to a node; this marks that the node should not accept any pods that do not tolerate the taints.

```yml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
  labels:
    env: test
spec:
  containers:
  - name: nginx
    image: nginx
    imagePullPolicy: IfNotPresent
  tolerations:
  - key: "example-key"
    operator: "Exists"
    effect: "NoSchedule"
```

A toleration "matches" a taint if the keys are the same and the effects are the same, and:
-   the `operator` is `Exists` (in which case no `value` should be specified), or
-   the `operator` is `Equal` and the `value` s are equal.

**Note:** There are two special cases:
An empty `key` with operator `Exists` matches all keys, values and effects which means this will tolerate everything.
An empty `effect` matches all effects with key `key1`.

# Node affinity and Pod affinity
# Node anti-affinity 
# Pod and deployment logs
`kubectl logs <pod_name>`

Describe a deployment and check the events

# kubectl events
# whats the deployment strategy ur using ?
blue-green
canary

# What is stateful set ?
# What is ingress ?

# Headless service ?

# Configmap vs Secret
secrets are encoded but not encrypted.

# How do you make sure data base start first and then application ?
we can define the logic for app pod/container to wait for the DB to come up and successful connection through readyness probe.

# liveness probe and ready ness probe

# types of storage classes ?
may be like SSD/HDD ?

# PV and PVC

# updating a password in secret will affect in POD/Deployment ?
# How to dynamically update the password in secret ?
# How to roll back deployment ?
https://www.youtube.com/watch?v=kFv6c00iEjY

# Whats the reason for pod eviction ?
Due to lack of resources on the node.
`kubelet` can reclaim the starved resource by failing one or more pods.
if evicted pod managed by a deployment, the deployment creates another pod to be scheduled by k8s.

# How your monitoring your cluster
using prometheus and grafana
> for application monitoring you need prometheus exporters
> for example prometheus exporter for kafka, prometheus exporter for linux

# Advanced
## How do you automate k8s deployment ?

![[Pasted image 20220318003732.png]]

## How do you secure your k8s app ?
K8s security
    - Application security
        - Pods, name spaces and nodes are secured with RBAC and IRSA.
    - Devsecops - Devops+Security = security of the container devops lifecycle
        - Authorization (using IAM roles)
        - scan repository
        - scan running container
    - Security compliance
        - FedRAMP,HIPAA,Soc etc..

## How do you cost/performance optimize your k8s app?
K8s cost
    - Control plane cost (fixed, not much room for improvement)
    - Worker node number and type
        - Pod resource specifications
        - Unused CPU/memory allocation
        - Detect CPU/Memory waste - utilize metrics server
           Analyzing metrics server data is not easy so use tools that helps in analyze the data.
           - Cloudwatch container insights - AWS
           - kubecost
           - CloudHealth
           - Kubernetes resource report

## Tell me about a challenge you faced in k8s ?
Challenge
    - K8s version upgrade 


# How to encrypt the traffic between pods using mtls protocol ?
using service mesh

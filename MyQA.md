```virtusa
How to make your webapp private?
how to call modules in the terraform files
lot on yaml based azure pipeline
	how to add trigger in yaml pipeline
	how to add pre/post approvals in yaml pipeline
	what are the tasks for sonar qube in yaml pipeline
how pipeline connects to azure artifacts
unble to access the azure key vault secrets, what could be the reason
azure hosted agent showing offline

```
```Cognizant
AKS
   kubernetes web hooks
   prometheus and grafana
   how to secure cluster
     by using RBAC
     enable SSL on service end points
   how to upgrade the cluster
   ELK ?
Docker
	RUN command vs entry point
Azure key vault
    how to backup azure keyvalut
     by replicating across regions
L3
---
whats the DR plan
how do you design the production grade cluster
	what are the question you ask different teams while designing
what are the issues faced while upgrading the cluster
```

```LTI
1. Azure networking
	1. express route
	2. vpn peering
	3. site site to vpn
2. Azure devops
	1. full life cycle
3. How to secure your environment
	1. azure
	2. AKS
4. what is the recent solution/project you delivered

```
```BT
1. Python/Shell scripting 
2. Terraform
	1. example code for resource creation
```

1. How do you monitor the AKS cluster?
2. Prometheus and Grafana?
3. Ingress controller and resource?
4. types of services?
5. Stateful vs stateless applications?
6. Daemon set and Cros jobs?
7. how to trouble shoot 502 error ?


11. Whats the branching strategy ur using?
12. how do you merge the code to main branch?

13. what are the services you worked on Azure ?
14. what are the services your created using terraform?
15. how to create AKS cluster with Terraform?

```
In general format
L1
what is CI/CD
what is k8s architecture

L2
how you are managing the secrets

L3
K8s
	whats the DR plan
	how do you design the production grade cluster
		what are the question you ask different teams while designing
	what are the issues faced while upgrading the cluster
AWS
	what are the vpc endpoints
	
```
```
Interview Tips
Always asks for feedback/suggestion at the end of the call.
```
```
AWS
which secret management u used
    how to use aws secret management
    how to use aws secrets in jenkins and k8s
aws lambda (server less)
        AWS AUST SCALING POLICIES
        s3 BUCKET POLICIES
        ROUTE 53 ROUTING POLICIES
        ec2 ROLES

aws IAM organizations

k8s cluster auto scaler
    how it scales , is it looks at limits or requests?
    k8s capacity planning
    how to select quorum
    how to update the k8s cluster
    how to take backup of k8s cluster/etcd
    how to take backup of all the deployments
    how to find the api version to use?

Helm
    helm2 vs helm3
    how to recover a deployment if I lost the values file

service
    how it selects the backend pods

limits and requests
how ingress controller works
    Storage
        how to expand a volume

Jenkins
    custom tools
    how to increase # of executors and what parameters we consider while increasing
    how to prioritose a job
Linux
    how to take a coredump
    how see system usage
    how to remove older files and error of arg list too long
Shell scripting
    error handling
    how to run a script in debug mode
    whats the use of -e option
    how to remove files older than a date
    df -kh vs du
Terraform
    How to see the preview - resource dependency hieranchy  
    null_resource
    lambda functions through tf
    terraform debug 
        not just setting the TF_LOG variable 
    terraform 0.13upgrade
    work spaces in TF
        how the main.tf and vars.tf are maintained
	implecit and explicit dependency
```

```
Azure devops
    how to create dependent jobs in AZ pipelines
        ude depends on
        may be conditions is the option
    how to integrate artifacts with pipelines
    email notifications
    reports
    Sonarqube for code coverage
    how to configure ISS role bindings
    how to deploy to different regions
        by using parrallel stages
    .net and nuget projects/deploymenst
    pass service
        webapp service
    classic and yaml pipelines
    variables and variable groups
    task groups
    whats the build tool for .net rpojects? VS Build
Azure
    IAM
        service principles and managed identity
    app gateway vs traffic manager vs standard load balancer
    how to monitor the network traffic in Azure
    how to recover the password for Azure vm (windows and linux)
    system-assigned managed identity
    traffic manager
    azure functions
    app gateway
    Azure front door
    Azure key vault
      How to backup
      How to replicate to different region
    
AKS
    how to implement blue green deployment with AKS
    https://azure.microsoft.com/en-in/solutions/kubernetes-on-azure/deployment-strategy/
    node pools
        do we assign node pools to clusters
        how to mention the nodepool in deployment
    monitoring
        https://www.containiq.com/post/aks-monitoring
        https://docs.microsoft.com/en-us/azure/aks/monitor-aks
    AKS cluster upgrade
        https://docs.microsoft.com/en-us/azure/aks/upgrade-cluster?tabs=azure-cli
    AKS cluster backup
    AKS maintanance activities
    pod identity
    how to secure k8s cluster
    Azure CNI vs KubeCNI
    secrets
	    how to use secrets from Azure key vault
	deployments
		variables
		how to use env variables from pipeline in deployment
	Service mesh
    
Git
    how to push a branch instead of main to remote branch instead of master
    how to configure webhooks
    repo/branch level roles for peer/manager approvals
    how to handle parallel releases
        git flow
        check the youtube video
    
Terraform
    how to resolve statefile conflicts
    workspaces
    terraform sentinel policies
    git flow
    what does terraform import do?
    how to create AKS cluster with Terraform?
    
powershell
    how to debug 
    some examples
        for loop
    
OTHERS
    Resource diagrams
    visio diagrams
    python
        check nanna youtube video - zero to hero
    Linux
        check edurekas 5 hour video
    shell scripting
        check youtube video on shell scripting examples
    Helm3
        check his udemy course on helm3 from AKS guy
    Git advanced use case - youtube video
    AKS tutorial
    https://docs.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-app
```
# General
- Whats your day to day activities
- Whats the recent issue you faced
- Explain about your project

## What's the artifacts tool your using
nexus

# Shell scripting
```
whats the recent automation you did?

sed
awk
```
## How to run a script in debug mode
`bash -x helloworld.sh`

## How to print 100 on the screen
```sh
#!/usr/bin/bash
for (( i=0; i<= 100; i++))
{
    echo "$i"
}

```

## sed
### how to read a particular line in a file
`sed -n 2p helloworld.sh`
`sed '2q;d' helloworld.sh` # This gives best performance as sed stops reading file after 2nd line

### How to replace a line in a file
`sed -i 's/old-text/new-text/g' input.txt`
`sed -i 's/"Hello world; $i"/"Hello world again; $i"/g' helloworld.sh`

### How to delete a line
`sed '1d' dummy.txt` # Delete first line
`sed '$d' dummy.txt` # Delete last line
`sed '1,5d' dummy.txt` # Delete range of lines
`sed '1d;2d;3d;$d' dummy.txt` # Delete multiple lines

# Git
```
webhooks
```

# Jenkins
```
- jenkins architecture
- whats the use of docker in jenkins pipeline
- what would be the reason if a job gets slowed suddenly
- 
- where the jenkins logs reside on linux and windows
https://www.jenkins.io/doc/book/system-administration/viewing-logs/
how to run parallel jobs
```
## Jenkins version ur using
2.289.3

## How to access the credentials in jenkins pipeline?
using `withcredentials` function.

## How to connect a jenkins slave to master?
Through SSH
Through jenkins web start (for windows)
Through jenkins as service on windowsmachine

## How to change the default port of 8080?
### On windows
```
java -jar jenkins.war --httpPort='xyz'  # for http
java -jar jenkins.war --httpsPort='xyz' # for https
```
### On linux
```
/etc/default/jenkins
add --httpPort=9999 or whatever port to JENKINS_ARGS
restart Jenkins with sudo service jenkins restart
```

## How to increase number of executors?
1.  Go to manage Jenkins.
2.  After that click om configure system.
3.  Inside configure Jenkins you can find `#of executors parameter`.
4.  Now you can set your desire executors.

# K8s
```
config maps and secrets
tainsts and tolerances
node affinity and anti affinity
how to make sure two pods from a deployment not to schedule on same node?
    by using pod anti affinity

monitoring: prometheus and grafana
whats the other way to set limits and requests than mentioning in deployment specs
what are the pod states
live ness probe, ready ness probe and what are the other probes
what happens when ready ness probe and liveness probe fails
when does these probes used

what are the security tools you use
    sonar qube
how do you use the cofnig maps
    as env vriables
    as mounting on to volumes
how do you scan ur images in k8s
how to backup and restore k8s, (i.e etcd)
coreDNS and default network in K8s
```

## K8s version your using?
1.23

## Docker version?
18.09

## Pods
### What happens when a new pod is created?
- Pod creation request can be submitted to k8s cluster through kubectl command or Pod definition yaml file
- kubectl communicates with kube api server for new pod creation
- Kube api server communicates with the kube scheduler to identify the suitable node for new pod
- Kube api server reaches the kubelet on the identified node
- kubelet creates the pod and updates the kubeapi server.
- kube api server saves the new pod status and its data in etcd data base.

### What are the POD phases/states ?
pending - it includes 
running
succeeded
failed
unknown

### Container states
waiting
running
terminated

## Nodes
## How to apply labels to nodes?
`kubectl label nodes <your-node-name> disktype=ssd`
`kubectl get nodes --show-lables`

## Ingress
### Where do you mention the ingress controller in yaml file?
Using annotation.

### How the app is accessed from internet through Ingress?
- app web address is entered in web browser
- It reaches load balancer IP through DNS server
- the request is processed by Ingress controller to direct it to right backend service
- service directs the requests to backend Pod

### Ingress controller vs Ingress resource?

## RBAC
## Role and Role binding?
## Cluster role and cluster role binding?

### example code
Deployment
```yml
ApiVersion: apps/v1
kind: Deployment
metadata:
  name:
  lables:
    app: webapp1
spec:
  replicas:
  selecotLables:
    app: webapp1
  template:
    containers
    - name:
      image:
      volumes:
      env:
       - name:
         keyRefFrom:
          
```
Service
SC
PVC

# AKS
## How to upgrade AKS cluster?
Check for the max surge setting
Check for the quotas for new nodes creation
Check for the Azure CNI IP pool for the available IPs
Create/Check for the PDBs

## Create AKS cluster using TF?

# AWS
- what are different types of IAM policies
- types of paths in Route 53
- how to replicate an EBS volume to another region
- how EC2 instance can access s3 bucket in different region
- types of EBS volumes
- how to know the traffic coming in to the VPC
- what are the VPC end points
- how to configure VPN
- how to get the new access key for EC2 instance
- SG vs NACL

# Azure
## How to prevent creating large VMs?
using azure policies
## What is azure policy?
Through which you can maintain the organizational standards and compliance.
## Storage
can blobs/containers be mounted on to VM ?

## Webapp
**How to make a webapp private?**
By creating private end points
https://learn.microsoft.com/en-us/azure/private-link/tutorial-private-endpoint-webapp-portal


# Linux
- List of open ports
- List of softwares installed
- what is the recent automation you did

# Docker
```
do you build the docker images
```
## What is multistage in docker
## How do you cleanup system
docker system prune
```
$ docker system prune

WARNING! This will remove:

    all stopped containers
    all networks not used by at least one container
    all dangling images
    all build cache

Are you sure you want to continue? Cy/N] y
```

## Dangling images
On the other hand, a **dangling** image just means that you've created the new build of the image, but it wasn't given a new name. So the old images you have becomes the "dangling image". Those old image are the ones that are untagged and displays "`<none>`" on its name when you run `docker images`.

## What is the issue you faced in docker?

# Terraform
```
Terraform
------------------
1.	
2.	
3.	
4.	

6.	
7.	
8.  
9.  
10. 
11. 
12. Difference between variable and variable.auto.tfvarf
13. How you will change the terraform version. 
14. What is terraform import?

Scenario:
13. We have already existing environment and now i want to create a new VM and should be create a new vnet and subnet for this VM and after 
    creating the vNet/sNet only VM should create. what you will do?
14.	If you want to call the existing resources to create any VM which function will use.
		
15. I have a additional data disk in my VM and wanted to destroy that data disk to using the Terraform code, it should not disturb any of the existing 		    configuration.		

16. Need to create a three VMs with different name like ending letter will be changed, how you will write a code?	

```

## What version of terraform you are using? 
v1.1.9 (n-1)

## What is terraform plan?
`terraform plan` is like a dry run, which compares the current infrastrutucture status in `terraform.tfstae` file with the desired configuration and shows the changes going to be applied by the `terraform apply`.

## What is the terraform providers?
Providers are the plugins through which terraform interacts with the underlying infra provider.
ex: Azure Providers (Azurerm), aws, and google.
## Complete process to deploy a terraform code?	
Start with Azure providers, resources, variables, explan about init, validate, plan and apply

## Terraform building Blocks?
Providers, Resources and Outputs

## How to import a resource created manually?
By using the `terraform import` you can import/add a resource to the `terraform.tfstate` file which was created in the cloud manually.
But this doesn't add the code/resource configuratio to the `tf` file and need to be added manually, otherwise terraform apply will delete the resource in next run.

## What is tfstatefile? and where did you store it?
tfstate file contains the current infrastrure state and we use remote backend to store it.

## How do you manage the remote state management?
By using the remote backend in the azure storage account.
```sh
# Configure Terraform remote State Storage
    backend "azurerm" {
    resource_group_name   = "terraform-storage-rg"
    storage_account_name  = "terraformstatexlrwdrzs"
    container_name        = "prodtfstate"
    key                   = "terraform.tfstate"
  }
```

## What are the terraform modules you worked on.?
Vnet 
VM
NSG
Storage

## What is tfvar file?
Variables are defined and assigned with default values using tfvars file.

## terraform functions?
toLower, count.index, depends on, locals, slice

## What is terraform workspace?

## How to create AKS cluster using terraform?
1. Define the pre requisites
	1. Size of the system node pool
	2. Size of the user node pools
	3. Type of the nodes in the system node pool, i.e DSV2
	4. Mention the username/password for windows node pool
	5. Create SSH keys for the linux node pools
	6. Create log analytics work space for the cluster monitoring
	7. Define the integrations with AD,ACR, key valut etc..
2. Create the configuration files
3. Run the files through build and release pipelines
	1. use Terraform task to run the init,plan and apply

## Sample code for creation of storage account?
main.tf
``` sh
# Terraform version 0.13 or later
# We strongly recommend using the required_providers block to set the
# Azure Provider source and version being used
terraform {
  required_version = ">= 1.1.0"
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "=3.0.0"
    }
  }
}

# Configure the Microsoft Azure Provider
provider "azurerm" {
    features {}
}
```
storage.tf
``` sh
resource "azurerm_resource_group" "grp" {
  name     = var.resource_group_name
  location = "North Europe"
}
 
resource "azurerm_storage_account" "store" {
  name                     = var.storage_account_name
  resource_group_name      = azurerm_resource_group.grp.name
  location                 = azurerm_resource_group.grp.location
  account_tier             = "Standard"
  account_replication_type = "LRS"
}

```

## Terraform provisioners?

# Azure DevOps
6. Task groups?
7. 
8.
9. 
10. 
12. Cron jobs in Azure devops?

## How to build the azure pipeline, end - end?
**Build Pipeline**
Select the source code
Select the type of the pipeline i.e .Net or Java
Select the OS to for agent to build the pipeline
Add tasks to Build the code
Add task to publish the artifacts for Release pipeline
Or Add task to build the docker image and push to ACR
Configure the trigger for continuous build.

**Release Pipeline**
Add the artifacts from Build pipeline
Configure the stages to deploy the code on to different environments , i.e Dev,QA,UAT or Prod
Configure the approvals and Gates per requirement

## Whats the build tool your using for .Net projects 
VS Build

## How to access ACR from pipeline?
Using service connection

## How to push the image to ACR?
By adding a task in build pipeline to Build and push the image to ACR

## How do you deploy to AKS?
Configure a service connection for Pipeline to connect to AKS
Publish the manifests files from Build pipeline
Use the manifests from build pipeline artifacts
Configure task to Deploy on to AKS

## Task groups for builds and releases (classic)

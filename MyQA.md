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

    Stoarge
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
GIT
    how to clone a private repo
    how to create a pull request
```

```
Azure devops
    how to create dependent jobs in AZ pipelines
        may be conditions is the option
    how to integrate artifacts with pipelines
    email notifications
    reports
Azure
    app gateway vs traffic manager vs standard load balancer
    how to monitor the network traffic in Azure
    how to recover the password for Azure vm (windows and linux)
AKS
    how to implement blue green deployment with AKS
    https://azure.microsoft.com/en-in/solutions/kubernetes-on-azure/deployment-strategy/
    node pools
        do we assign node pools to clusters
        how to mention the nodepool in deployment
    monitoring
        https://www.containiq.com/post/aks-monitoring
        https://docs.microsoft.com/en-us/azure/aks/monitor-aks
Git
    how to push to remote branch instead of master
```
# QA with Dyan
```
Cloud
how many subscriptions are there?
    whats the subscription type?
    enterprise or pay-as-you-go
how to open a support ticket?
    whats the details they might ask, like logs or any files from us or from our account?

AKS
how you are monitoring your AKS cluster ?
are you using Azure container registry ?
How you are doing ur unit testing when you write new yaml files for CI/CD or AKS?

GIt
    how to create a  branch, are you creating a branch for every change you do ?
    and are you creating a pull request ?
    
    how the code review and approvals happens ?
    are you using pull requests to merge the code
CI/CD
are you using any build tools?

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
`sed??'1d'??dummy.txt` # Delete first line
`sed '$d' dummy.txt` # Delete last line
`sed??'1,5d'??dummy.txt` # Delete range of lines
`sed??'1d;2d;3d;$d'??dummy.txt` # Delete multiple lines

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
add??--httpPort=9999??or whatever port to??JENKINS_ARGS
restart Jenkins with??sudo service jenkins restart
```

## How to increase number of executors?
1.  Go to manage Jenkins.
2.  After that click om configure system.
3.  Inside configure Jenkins you can find??`#of executors parameter`.
4.  Now you can set your desire executors.

# K8s
```
config maps and secrets
tainsts and tolerances
node affinity and anti affinity
how to make sure two pods from a deployment not to schedule on same pod
    by using pod anti affinity
how to apply labels to nodes
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
1.19

## Docker version?
18.09

## What are the POD phases/states ?
pending - it includes 
running
succeeded
failed
unknown

## Container states
waiting
running
terminated

## Ingress
### where do you mention the ingress controller in yaml file?
Using annotation.
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
On the other hand, a??**dangling**??image just means that you've created the new build of the image, but it wasn't given a new name. So the old images you have becomes the "dangling image". Those old image are the ones that are untagged and displays "`<none>`" on its name when you run??`docker images`.

## What is the issue you faced in docker?

# Terraform
```
sample code for creation of s3 bucket
```
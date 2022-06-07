```
which secret management u used
    how to use aws secret management
    how to use aws secrets in jenkins and k8s
aws lambda (server less)

k8s capacity planning

aws organizations
k8s cluster auto scaler

```
# General
- Whats your day to day activities
- Whats the recent issue you faced
- Explain about your project

## What's the artifacts tool your using
nexus

# Shell scripting
```

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

# Jenkins
```
- jenkins architecture
- whats the use of docker in jenkins pipeline
- what would be the reason if a job gets slowed suddenly
- 
- where the jenkins logs reside on linux and windows
https://www.jenkins.io/doc/book/system-administration/viewing-logs/
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
how to make sure two pods from a deployment not to schedule on same pod
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
- 
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
sample code for creation of s3 bucket
```
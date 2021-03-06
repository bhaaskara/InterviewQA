# What is the functionality of a hypervisor?
A hypervisor provides virtualization at hardware level.
It enables us to share hardware with multiple guest VMs. 
i.e use a single host computer to support multiple guest virtual machines.

There are two types of hypervisors
- Type 1 - Bare metal/Native hypervisor
- Type 2 - Hosted hypervisor

# What is Containerization
An application and all its dependencies bundled together, so the application runs reliably across computing environments.

# Virtualization vs Containerization
Virtualization enables you to run multiple operating systems on the hardware of a single physical server, 
while containerization enables you to deploy multiple applications using the same operating system on a single virtual machine or server. 

Containerization is virtualization at OS level.
Virtualization is virtualization at hardware level.

# What is Docker
Docker is a Containerization platform which packages your application and all its dependencies together in the form of containers, to ensure that your application works seamlessly in any environment be it Development, Test or Production.

# What is a container ?
Container include the applications and all of its dependencies, running as isolated processes in user space on the host operating system, and shares the kernel with other containers.
Container is the running instance of Image.

![[Pasted image 20220305225910.png]]

# What is Docker/Container Image
Docker/Container image is the source for container, in other words docker images are used to create containers. 
convenient way to package up applications and preconfigured application environments,
that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

`Container images become containers at runtime and in the case of Docker containers - images become containers when they run on Docker Engine.`

# What is docker file
A Docker file is **a template that contains a set of instructions for creating an image that can run on the Docker platform**

![](Pasted%20image%2020220517114109.png)

# What is docker hub ?
Docker hub is the registry where docker images live.

# What is docker compose ?
Docker Compose is **a tool that was developed to help define and share multi-container applications**. With Compose, we can create a YAML file to define the services and with a single command, can spin up everything, or tear it all down.

# Where are docker volumes stored ?
Volumes are stored in a part of the host filesystem which is managed by Docker ( **`/var/lib/docker/volumes/`** on Linux).

# What does the docker info command do?
**displays system wide information regarding the Docker installation**. 
Information displayed includes the kernel version, number of containers and images.

# List the most commonly used instructions in Dockerfile?
FROM: You must have noticed that almost all the dockerfile starts with the FROM command.
RUN : run specified commands.
CMD: ENTRYPOINT

# Difference between RUN and CMD ?
# Difference between ADD and COPY
COPY : lets you copy a file from src to dest (Docker image)
ADD : you can copy a file and you can use URL instead of file/dir and also you can copy tarfile to an image.

# Difference between CMD and entry point ?

# Can you differentiate between Daemon Logging and Container Logging?
Docker container logs are **generated by the** Docker containers. They need to be collected directly from the containers.

# What is the best way of deleting a container?
`docker stop <Continer ID> & docker rm -f <Container_ID>`

# What is docker swarm ?
Docker swarm is native clustering for Docker.
Docker Swarm is a container orchestration tool that allows us to manage multiple containers across different host machines.

# How do you build a Dockerfile?
using `docker build` command

# How do you ensure that container 1 runs before container 2 while using Docker Compose?
using `depends-on`

# What platforms does Docker run on ?
All linux platforms
Windows and mac are supported on for dev, not for production.

# How many containers are running ?
`docker ps`

# docker logging driver ?
# what is the difference between bridge network and custom bridge network ?
# Difference between overlay and host network ?
# what is port forwarding and when do u use it ?
# what is docker system prune and image prune ?
# how many types of volumes are there in the docker ?
# how to check image vulnerability ?

# What is namespace ?
Namespace adds a layer of isolation in containers.
its an important feature of linux and an important concept of containers.

# What is the lifecycle of a docker container?

# Docker command questions ?
## How to know docker client and server version
`docker version`

## Detailed info about the installed docker ?
`docker info`

## How to know number of running, paused and stopped containers ?
`docker info`

## How to login to the docker hub
`docker login`

## How to create a docker container out of a image
`docker run -it -d <img_name>`

## List all the running containers
`docker ps`

## How to access a running container ?
`docker exec -it <cont_id> bash`

## How to start, stop and kill a container ?
```sh
docker start <cont id>
docker stop <cont id>
docker kill <cont id>
```
## Can you use a container, edit it and update it ?
`docker commit <cont_id> <username/image_name>`

## How to push image to docker hub ?
`docker push <username/imagename>`

## How to delete a stopped container?
`docker rm <cont_ID>`

## How to delete an Image ?
`docker rmi <image_id>`

## How to build a docker file ?
`docker build <path to docker file>`

# What is docker prune ?
It cleans up unused docker objects.
`docker system prune`
- will remove all stopped containers
- will remove all dangling images
- will remove unused networks
- will remove build cache

# Will you loose your data once docker container exits ?
No, it will be there until container is removed.

# Can you remove a paused container ?
No, container has to be in stopped state before it can be removed

# Can a container be restarted by itself ?
No, by default the flag `-restart` is set to false.

# How to monitor docker containers in prod ?
`docker stat` - memory and CPU stats
`docker events` - provide event 

# What changes are expected in your docker compose file while moving it to prod ?
- remove volume bindings
- binding to different ports on the host
- specify a restart policy
- add extra services like log aggregator

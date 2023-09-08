---
alias: 
tags:
- published
- index/23.05
---

Easiest explanation: [Never install locally](https://youtu.be/J0NuOlA2xDc)

Udemy course: [Docker containers](https://www.udemy.com/course/docker-containers/)

# Container

Unit of software that packages up code and all its dependencies so you can run it in one environment and it includes everything to run the app. It's different from a VM.

# Docker Containers and the Docker Engine

**Docker container** - isolated environment running within a host machine's kernel to allow running application specific code

**Kernel** - software at the core of an OS. Linux, WindowsNT etc. Docker runs on top of original machine's kernel. 

**Docker engine** - docker server, API and command line interface. For Docker, this is *docker daemon*.

**daemon** - background process on an OS. processes that run unattended.

**Docker CLI** - allows interaction with Docker daemon.

![b51b312987826ebd92a02be3b8b3cebd MD5](https://i.imgur.com/ld6CElG.png)

## Docker Container Environments

- Independent file systems and local networks
- Run application-specific code

# Containers vs VM

- both used for isolated environments
- VMs abstract the whole OS
- containers are smaller and only isolates file systems and networks. can share common files and systems

# Docker Images

- read only template with instructions for creating the docker container
- define the container code, libraries, env variables, config files etc

## Docker file

- outlines the instructions for how the image will create the docker container
- you can use one image for multiple containers

## Dockerhub

- contains docker images as repositories online

# Installing Docker

See: [docker install link](https://docs.docker.com/desktop/install/windows-install/)

This requires [[Enabling WSL on Windows]]

# Creating a container

Run `docker create --name=foo -it ubuntu bash` from terminal

![4b1987a7d3ea07387bfb1dc85958efe7 MD5](https://i.imgur.com/DOOo3fq.png)

![ae7786731cabdbdc504fff6ce9e2fba2 MD5](https://i.imgur.com/qkRDEha.png)

## Starting the container

Run using `docker start foo`
.
![befe90bcb918357c10c1fc61b59e0e85 MD5](https://i.imgur.com/utCOcky.png)


# Docker
![Docker logo](https://i.imgur.com/p3Rf0J8.png)

## What is Docker?
- Open platform for developing, shipping, and running applications
- It enables you to separate your applications from your infrastructure so you can deliver software quickly
- Can automate the deployment of applications as portable, self-sufficient containers that can run on the cloud or on-premises

## What are Docker containers?
Standardised, executable components that combine application source code with the operating system (OS) libraries and dependencies required to run that code in any environment3.

## Installation
Source: <https://github.com/khanmaster/docker_setup>

Run `docker --version` to make sure it's installed.

![docker --version](https://i.imgur.com/I95TrkN.png)

Make sure the **Docker Desktop** app is downloaded and Docker is running.

## How does a Docker API work?
Docker provides a REST API that allows you to interact with the Docker daemon.

The Docker Engine API is accessed by sending HTTP requests to the Docker daemon.

The API uses standard HTTP verbs such as GET, POST, PUT, and DELETE to perform operations on resources such as containers, images, and networks.

## Image and Container Setup
![Docker Architecture](https://i.imgur.com/vZZ6XQP.png)

Use `docker` to see a list of useful docker commands.

`docker images` lists the Docker images.

Entering `docker run hello-world` will allow the Docker daemon to get the image from the registry and run it in the local machine.

![Hello World](https://i.imgur.com/Hdq7HAg.png)

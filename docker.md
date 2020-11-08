# Docker

Dockers only runs over the layers of apps instead virtualising the whole OS kernel.

## What is a container?

A container is a layer of images, also is an image that is running. The running environment specifically.

The container has a port attached to it, so you can communicate with the app.

## What is an image?

An image is a package of an app, with its configuration and starter script for example.

## Some basic commands

- *docker ps* list all running containers
- *docker ps -a* list all running containers
- *docker images* list all pulled images
- *docker pull <image-name>* pulls (download) an image app

### Docker run

Creates a new container from an image app, if it doesn't exists locally, docker will pull it.

### Some useful parameters

- *\-d* runs in detached mode
- *\-p[local_host:app_port]* binds a local host port to the app port
- *\-\-name [name]* gives a name to the container
- *\-e [VARIABLE]* sets environment variables for container
- *\-\-net [network_name]* append container to this given network

### Related commands to containers

- *docker start <container-id>* starts an existing container
- *docker stop <container id>* stops the running container
- *docker logs <container-id, name>* outputs logs from container
- *docker exec -it <container-id, name> /bin/bash or sh* opens the terminal from the given container, it stands for interactive terminal

## Docker network

Running containers have its own network, isolated from the **host** machine network.

### Options

- *create [name]* will create a new network
- *ls* list all created networks

## Docker volumes

Volumes are plugs to the container virtual file system anad host file system.

There are 3 types of volumes:

- *anonymous* (generated and mounted automatically by docker)
- *referenced* (specifying a path to container path, *host/app:container/app*
- *named* (given a name, this will allow to connect containers file systems more easily, *name:container/app*)

Everytime a container is restarted or deleted, their data is erased. To persist it, a volume must be configured.

## Docker file

This *Dockerfile* is a blueprint for building an image. Specifying things like image layer, environment variables, run commandn, copy directorys, among others and a entrypoint command.

Example:

```
FROM python:3.6

ENV USER=user

RUN mkdir -p app/src

COPY src app/src

CMD["python", "app/src/main.py"]
```

*Note: Updating the app requires to build again the image*

[Docker build reference](https://docs.docker.com/engine/reference/commandline/build/)

## Docker compose

It's a tool for orchestrating containers, where you specify your services (containers) and images, ports, networks, environment variables, among other configuration parameters. Must be declared on a **YAML** file.

Example:

```
version: "3"

services: 
nginx:
 image: nginx:alpine
 container_name: nz01
 ports: - "8000:8000"
 volumes:
  - ./src:/src
  - ./config
 depends_on:
   - web
networks:
 - djangonetwork
 .....
```

[Docker compose reference](https://docs.docker.com/compose/reference/)

## Good references

[Removing images and containers](https://www.freecodecamp.org/news/how-to-remove-images-in-docker/)

[Removing images, containers and volumes](
https://www.digitalocean.com/community/tutorials/how-to-remove-docker-images-containers-and-volumes)

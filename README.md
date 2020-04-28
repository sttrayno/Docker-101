# Docker 101 - Getting started with containers

Introduction guide to getting started with Docker containers


## Prerequsites

To do this lab you'll need a system with Docker installed, if you don't already have it installed follow the link below which will take you through installing docker for your platform

https://docs.docker.com/get-docker/

When docker is sucessfully installed you should be able to run the ```docker --version``` command to verify that the docker daemon is running.

```
docker --version
```

![](https://github.com/sttrayno/Docker-101/blob/master/images/docker-v.gif?raw=true)


Alternatively, you can use an in-browser Docker playground called www.play-with-docker.com. The play-with-docker.com site provides access to a full VM running Docker directly in a web browser, making it easy to work with Docker from any device.

To use this open www.play-with-docker.com on a browser the site displays a Captcha dialog to ensure that you're not a robot. Press Play and complete the Captcha to continue. The play-with-docker site displays a session countdown and an Add New Instance button. 

Click the Add New Instance button. The site creates and displays a terminal session in the browser. The rest of this learning lab uses the in-browser terminal session to work with Docker.

## Step 1 - Hello world

The simplest way to use Docker is to run an existing public image that's available from Docker Hub.

Docker Hub is a public exchange for sharing Docker containers. Other container sharing sites are available, but we'll take advantage of the fact that Docker's command-line interface searches DockerHub by default. Dockerhub is by far the most common and the largest

To run a publicly-available Docker Container, follow these steps:

Search for a container named "hello-world." Use the command docker search hello-world to find the "hello-world"" image:

```
docker search hello-world
```

![](https://github.com/sttrayno/Docker-101/blob/master/images/hello-world.gif?raw=true)

Docker searches the public DockerHub repositories and finds the "hello-world" image. You can see theres a few however theres only one with the name hello-world, so lets run it with the command:

```
docker run hello-world
```

![](https://github.com/sttrayno/Docker-101/blob/master/images/run-hello-world.gif?raw=true)


Docker first checks to see whether the "hello-world" image is available locally. If not, Docker automatically downloads it from DockerHub. Docker sets up the container to run locally, including ensuring its isolation from other processes. Once the preparations are made, Docker runs the image.

Congratulations! You just ran your first Docker container!

## Step 2 -  A look at the dockerfile

Now we've ran our first container sucessfully and we know our docker environment is working well it's time to start to go a little more into the key concepts. One of the first concepts you need to understand to do anything with containers is the concept of the dockerfile.

Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image.

An example dockerfile might look like below. For a full list of commands and details around what you can do in a dockerfile follow [this link](https://docs.docker.com/engine/reference/builder/)

```
FROM ubuntu
RUN apt-get update
RUN apt-get -y install python
````



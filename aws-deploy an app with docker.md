<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Deploy an App with Docker

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-compute-eb)

**Author:** muluthukubura@gmail.com  
**Email:** muluthukubura@gmail.com

---

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-compute-eb_c4df13c84)

---

## Introducing Today's Project!

### What is Docker?

Docker is a platform that allows developers to package applications and their dependencies into lightweight, portable containers. It is useful because it ensures consistency across different environments and simplifies deployment and scaling.

### One thing I didn't expect...

One thing I didn't expect in this project was seeing how quick it is to deploy an application using AWS Elastic Beanstalk.

### This project took me...

This project took me approximately 2 hours.It was most rewarding to see the containerized application run successfully, as it proved that I had correctly set up the environment and applied Docker concepts in practice.

---

## Understanding Containers and Docker

### Containers

Containers are tools for packaging applications in a way that easy for developers to run. They are useful because they help developers/Engineers to share their work more efficiently.

A container image is a template or a blueprint for creating a container. use a container image container spawned/created from the same  image will behave in a same way which helps teams of developers having a unified experience in running same app

### Docker

Docker is a platform for creating and managing containers. Docker makes working with containers easy. Docker Desktop is software for using/interacting with Docker.Docker Desktop makes working with Docker itself easy. 

The Docker daemon is like the engine for Docker that receives the commands we send through clients in the Docker Desktop or the text command sent in the terminal and actually creates/manages/controls the containers.

---

## Running an Nginx Image

Nginx is a web server/software that helps with serving web content. Nginx is often refer to as a proxy server, which means it helps with distributing traffic to your application across the instances running  your application.

The command I ran to start a new container was docker run and also set the flags -d -p  80:80  nginx, whic means running the container in the background and matching port 80 on our host computer to the container's port 80. 


![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-compute-eb_6245f5bb10)

---

## Creating a Custom Image

The Dockerfile is a set of instructions that tell Docker to build a custom container image.

My Dockerfile tells Docker three things. First, our custom image uses the latest version of the nginx container image at its base. Then we are modifying this base by replacing the default nginx welcome page with our own custom index.html

The command I used to build a custom image with my Dockerfile was [Docker build -t my-web-app .].The '.' at the end of the command means that Docker can find the Dockerfilein the current directory.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-compute-eb_4c741d1913)

---

## Running My Custom Image

There was an error when I ran my custom image because a running container is already using port 80. I resolved this by stopping the running container so that I can start the new one.

In this example, the container image is the template for creating a new container running at Nginx server that serves our custom index.html file. The container is the actual software running at Nginx web server with those customizations

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-compute-eb_74b5c3d619)

---

## Elastic Beanstalk

Elastic Beanstalk is an AWS service that helps with deploying applications to the cloud. It abstracts away a lot of the ways of setting up the cloud infrastructure when deploying applications.

Deploying my custom image with Elastic Beanstalk took me 10 minutes

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-compute-eb_26d5573b23)

---

## Deploying App Updates

---

---

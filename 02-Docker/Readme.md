## Assessment Questions and Answers

### 1. What is docker and why do we need it?
 
**Ans**: Docker is a platform used for building, running, managing, and distributing applications as portable containers. On the other hand, containers
are lightweight, isolated environments that contain an application and its dependencies. Docker provides a lightweight, portable, and efficient solution 
to build, ship, and run applications. Docker is a popular tool for DevOps because it help us to:
- Simplify application deployment: Containers can be deployed to an environment that has Docker installed, making it easy to move applications between development,
  staging, and production environments.
- Improve Efficiency: Containers ensure that applications are deployed with all of their dependencies, so there are no issues when an application is been deployed to an particular environment.
- Increase resource utilization: Containers are lightweight and share the host operating system, so they use fewer resources than traditional virtual machines.


### 2. Write a docker file for a sample Java/python application.

**Ans**: Below provided Dockerfile is for an simple todo application built with Django.
```
FROM python:3

RUN pip install django==3.2

WORKDIR /app
COPY . /app

RUN python manage.py migrate

CMD ["python","manage.py","runserver","0.0.0.0:8000"]

```

### 3. What is the docker lifecycle?
   
**Ans**: The Docker lifecycle consists of the following stages:
- Create: A container is created from a Docker image.
- Run: The container is started and its processes are executed.
- Pause: The container's processes are paused, but the container itself is still running.
- Stop: The container's processes are stopped, and the container is no longer running.
- Kill: The container is forcibly terminated, and its processes are killed.
- Remove: The container is deleted from the Docker host.
   
### 4. What is the difference between an image and a container?

**Ans**: 
A **Docker image** is a read-only template that contains the instructions for creating a container. 
An image is like a blueprint for a container. It contains all of the files and commands that are needed to run an application which includes 
application's code, libraries, and dependencies Whereas a **container** is an instance of a Docker image. 
It is a running process that is isolated from other containers and the host operating system.

### 5. How to check docker container logs? Provide the command for the same

**Ans** : 
To check the logs of a Docker container, we can use the following command
```
docker logs <container-id> 
```

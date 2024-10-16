# Docker Crash Course
```qrcode
[YouTube](https://youtu.be/pg19Z8LL06w?si=fmt3mBic6KsbBCsr)
```

[YouTube](https://youtu.be/pg19Z8LL06w?si=fmt3mBic6KsbBCsr)
## Intro and Course Overview

Chapter 1 of the article provides an overview of Docker, explaining its purpose in software development and deployment. It covers the differences between virtual machines and Docker, the advantages of using Docker, and the basic concepts of Docker images, containers, and registries. The chapter also includes practical exercises on installing Docker, working with images, and running containers.

## What is Docker?

Chapter 2 of the article explains that Docker is a virtualization software that simplifies the development and deployment of applications by packaging them into containers. This container includes everything the application needs to run, such as code, libraries, dependencies, and runtime environment configuration. Before Docker, applications were developed and deployed separately, making the process more complex and time-consuming. Docker streamlines this process by providing a single package that can be easily shared and distributed.
- Visualization software
- Makes developing and deploying application much easier
- Packages application with all necessary dependencies configuration, system tools and runtime
- Portable artifact, easily shared and distributed

>A Standardized unit, that has everything the application need to run
## What problems Docker solves in development and deployment process

Chapter 3 explains the traditional way of developing and deploying applications before containers, where developers had to install all the necessary services directly on their operating system. This process was complex and error-prone, especially when multiple developers with different operating systems were involved. Containers, like Docker, simplify this process by packaging all the services and dependencies into isolated environments, making it easier to develop and deploy applications. With containers, developers no longer need to install services directly on their machines, and operations teams can easily deploy applications by running Docker commands. This standardized process reduces errors, conflicts, and communication overhead between development and operations teams.
### Development Process before containers
- [c] Installation process different for each OS environment
- [c] Many steps, when something can go wrong
- [c] If your application use 10 services, Each developer needs to install these 10 service
### Development process with containers
- Own isolated environment
- Postgres package with all dependencies and configs.
- [p] Start service as a docker container using a 1 Docker command
- [p] Command same for all OS
- [p] Command some for all services
- [p] Easy to run different versions of same app without any conflicts

>Standardizer process of running any service on any local dev environment
### Deployment process before containers
**Development => Operation (Jar files, Database)**
- Artifact and instructions handed over ops team
- Ops team handles installing and configuration apps and its dependencies.
- [c] Installation and configuration done directly on the server's OS
- [c] Dependency version conflicts etc..
- [c] Human error can happen
- [i] Textual guide for deployment 
### Deployment process with containers
- Docker artifact includes everything the app needs
- [p] No configuration needed on the server (Except docker runtime)
- [p] Less room for error
- [i] Instead of textual, everything is packaged inside the docker artifact
**Ops team works,**
- Install Docker runtime on the server.
- Run docker command to fetch and run the docker artifact.
## Virtual Machine vs Docker

Chapter 4 of the article discusses the differences between Docker and virtual machines in terms of virtualization. Docker virtualizes the application layer of the operating system, resulting in smaller image sizes and faster startup times compared to virtual machines. However, Docker containers are not as compatible across different operating systems as virtual machines. Docker desktop for Windows and Mac allows running Linux-based containers on non-Linux operating systems by using a lightweight Linux distribution on top of a hypervisor layer.
### what is VM
A Virtual Machine (VM) is _a compute resource that uses software instead of a physical computer to run programs and deploy_ apps.
### How an OS is made up
**2 main layers**
1. OS application layer
2. OS Kernel layer
![[DOCKER 🐳 - techworld with nana 2024-03-12 22.22.20.excalidraw]]
### Install Docker

Chapter 5 of the article discusses the installation of Docker. It emphasizes the importance of referring to the latest documentation for installation guides due to frequent updates. Docker Desktop is recommended for running Linux-based images on different operating systems and includes the Docker engine, command line interface client, and graphical user interface client. The chapter provides step-by-step instructions for installing Docker on Mac, Windows, or Linux, and explains the concept of images in Docker.

### Docker Images vs Containers

Chapter 6 of the article explains how Docker allows for packaging applications with their environment configurations into Docker images, which can be easily shared and distributed. These images contain not only the application code but also information about the environment configuration, such as operating system and tools like Node.js or Java runtime. When an image is downloaded and run on a computer, it creates a container, which is a running instance of the image. Multiple containers can be created from the same image for increased performance. The chapter also mentions the availability of a Docker command line interface client for interacting with the Docker engine. Additionally, it briefly introduces Ned Hopper's Cloud platform called Kubernetes Application Operations, which offers a way for DevOps teams to manage and monitor applications in multiple Kubernetes clusters.

### Docker Registries

Chapter 7 of the article discusses Docker Registries, which are storage platforms specifically for Docker images. These registries contain ready Docker images that can be easily accessed online, including official images created by companies like MongoDB or the Docker Community. Docker Hub is highlighted as the largest Docker registry, where users can find a wide range of official and user-created images for various services. The chapter emphasizes the importance of Docker's dedicated team in reviewing and publishing official images to ensure they meet security and production best practices. Users can browse and access these images on Docker Hub without the need for registration.

### Docker Image Versions

Chapter 8 discusses the concept of image versioning in Docker. When technologies like Redis or MongoDB release updates, new Docker images are created with version tags. Users can choose specific versions of images by selecting the appropriate tag, with the "latest" tag representing the most recent image. The chapter also explains how to locate and download Docker images from Docker Hub, using Nginx as an example for setting up a container locally. Selecting a specific image version is recommended for best practices.

### Main Docker Commands - Pull and Run Docker containers

Chapter 9 explains how to download Docker images using the "docker pull" command, specifying the image name and version tag. It also covers running containers based on these images using the "docker run" command, with the option to run containers in detached mode to avoid blocking the terminal. Additionally, the chapter demonstrates how to view container logs and run containers directly from Docker Hub without needing to download the image first. Multiple containers with different versions of the same application can be run simultaneously using Docker.

### Port Binding

Chapter 10 explains how to access a Docker container running on a closed Docker network from a local computer browser by exposing the container to the local network through port binding. This involves specifying the container's port (e.g., Port 80 for nginx) and binding it to a specific port on the local host (e.g., Port 9000). By using the "-p" flag when creating a new container, the container's application can be accessed as if it were running on the local host. This allows users to access the container's application from a browser on the specified port (e.g., localhost:9000 for nginx).

### Start and Stop containers

Chapter 11 discusses how to manage Docker containers effectively, including accessing logs, stopping and restarting containers, and assigning meaningful names to containers for easier management. The chapter explains how to use container names instead of IDs for various Docker commands, as well as how to stop and restart containers without creating new ones. It also introduces the "--name" flag for giving containers specific names during creation, making it easier to identify and manage them.

### Private Docker Registries

Chapter 12 discusses the concept of private Docker registries, which allow companies to store their own Docker images securely without making them publicly available. Various cloud providers offer private Docker registry services, such as AWS ECR, Google Cloud, and Azure. Docker Hub also provides the option to create private registries for storing images. The chapter explains how users can create private registries on Docker Hub and upload their own images for secure storage.

### Registry vs Repository

Chapter 13 explains the difference between a Docker registry and a repository. A Docker registry, such as AWS ECR or Docker Hub, is a service that provides storage for images. Within a registry, there can be multiple repositories for different application images. Each application has its own repository where different image versions or tags can be stored. This distinction helps users understand how to organize and manage their Docker images effectively.

### Dockerfile - Dockerize Node.js app

Chapter 14 discusses the process of creating a Docker image for a custom application. This involves writing a Dockerfile that defines how the image should be built, including specifying a base image (such as one with Node.js installed), installing dependencies, copying application code into the container, setting a working directory, and running the application. The Dockerfile outlines the steps needed to package the application code into a Docker image that can be deployed as a container.

### Build Image

Chapter 15 explains the process of building a Docker image from a Dockerfile. The chapter details the Docker build command, which allows users to specify the name and tag of the image, as well as the location of the Dockerfile. It also covers running a container from the newly created image, including exposing ports and accessing the application within the container. The chapter concludes with verifying the application is running successfully by accessing it through a web browser and checking the container logs.

### Docker UI Client

Chapter 16 discusses the graphical user interface (GUI) client provided by Docker Desktop. The GUI allows users to view and manage containers and images, providing an overview of running and stopped containers, as well as the ability to start, stop, restart, or delete containers. Users can also create containers directly from the GUI. The chapter acknowledges that some users may prefer the command line interface, but the GUI offers a visual alternative for those who are more comfortable with it.

### Overview: Docker in complete software development lifecycle

Chapter 17 provides a detailed overview of how Docker fits into the complete software development and deployment process. It explains how Docker can be used in various stages, from local development to testing and deployment on development servers. The chapter outlines a simplified scenario where a JavaScript application is developed locally, tested, and deployed using Docker containers, private repositories, and continuous integration tools like Jenkins. It highlights the importance of Docker in streamlining the software development lifecycle.

### Where to go from here

Chapter 18 delves into the more advanced aspects of Docker, such as connecting applications to Docker containers, using Docker Compose, Docker volumes, and more. The chapter also mentions that for those looking to further enhance their Docker skills and learn about integrating Docker with other technologies like Jenkins, Terraform, and Ansible, they can explore the complete DevOps bootcamp offered by the author.
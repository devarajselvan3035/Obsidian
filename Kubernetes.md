[**Tech-world with nana - Kubernetes basics - 1hrs video(YouTube)**]("https://youtu.be/s_o8dwzRlu4?si=kAhYGDMv0HIWNRs6")

```qrcode 
https://youtu.be/s_o8dwzRlu4?si=pDOoHeL3ddwRcq9F
```
# Kubernetes
- Kubernetes is an open-source container orchestration system for automating software deployment scaling and management.
- Designed by ==Google==
- Helps manage containerized application in different deployment
- environments *Ex: physical, cloud, hybrid*
## Need for container orchestration tool
- trend from monolith to microservice
- Increased usage of containers.
- Demand for a proper way for managing those hundreds of containers
## What features do orchestration tools offer...?
- High Availability or no downtime 
- Scalability or high performance
- Disaster recovery - backup and restore
## Worker node
**API server** => Entry-point to K8s cluster
**Controller Manager** => Keep track o what's happening in the cluster
**Scheduler** => Ensures pods placement
>Scheduler decides o which node new pod should be scheduled

**ETCD** => Kubernetes backing store[^etcd]
**Virtual Network** => Creates one unified machine
>node = Virtual or physical machine

___

## Main Kubernetes Components:
1. pod
2. Service
3. Ingress
4. Configmap
5. Secret
6. Deployment
7. Statefulset
8. Daemonset

### pod
- Smallest unit in kubernetes
- Abstraction over container
- usually 1 application per pod
- Each pod gets its own Ip address
- New Ip address on re-creation
- A Group of one or more containers
- Ip address and pod or connected

>Pods are ephemeral. You can only interact with the kubernetes layer

### Service
- Permeant Ip address
- Life cycle of pod and service not connected
- To group a set of **pad endpoints into single resource**
- Load Balancer
### Ingress
An API object that helps developers expose their application and manage external access by providing https routing rules to the service with a kubernetes clusters.
### Configmap
An API object that lets you store configuration for other object to use unlike most kubernetes object that have a spec, a configmap has data and binary data fields. These fields accept key-value pairs at their values. Both the data field and the binary Data are optional.
>Configmap is for non-confidential data only

### Secret
- Used to store secret data *Ex: Password, Certification, credentials*
- Base 64 in encoded format
- Reference secret in Deployment pods

### Volume
- Storage on local machine
- On remote, outside of the K8s cluster.

> Kubernetes doesn't manage data persistence

If the endpoint of the service name in change to different database(Mongo-DB) at the time you ca
- Rebuild the application
- Push it to Repository
- Pull it in your pod => Restart everything
### Deployment
- Define blue print of pods.(Blueprint application pods)
- Specify how many replicas you want to have
- You create deployment
>Database can't be replicated via deployment

>[!note]
>Deployment = For stateless app
>Statefulser => For statefulapps or Database

### Statefulset
- Runs a group of pods and maintains a sticky identity for each of those pods
- This is very useful for managing application that need persistent storage or a stable, unique network identity
- Statefulset is the workload API object object manage stateful application

## Kuberbetes Configuration

![Example](https://www.armosec.io/wp-content/uploads/2022/02/Picture1-3.png.webp)

Example of Configuration Json and YAML files

### Kubernetes Configuration (Kubeconfig) file
A yaml or Json file contains group of clusters, users and contexts. A context is a combination of a cluster and user.

### 3 parts of a K8s configuration file
1. Metadata
2. Specification 
3. Status
>ETCD holds the current status of any K8s components

### YAML Configuration file
- Human friendly data serialization standard for all programing language
- Syntax: strict indentation
- Stored the config file with your code or own git repository

## Minikube and Kubectl
### Production cluster setup
- Multiple master and worker nodes
- Separate virtual or physical machine
![](https://dz2cdn1.dzone.com/storage/temp/11199835-clusters.png)
### Minikube
Basically one nod cluster where master process and the worker processes both run one node and this node will have docker containers

### Kuberctl
- Command line tool for K8s cluster
- Used to urn commands against kubernetes cluster
- It does this by authenticating with the master node of your cluster and making API calls to do a variety of management action

## Install and Create Minikube cluster
Command for creating minikube
```command shell
brew install minkkube
```
- Minikube has docker pre-installed to run the containers in the cluster
- Driver means e are hosting minikube as a container on our local machine

## Mongo-DB Config
### Configmap configuration file
**-kind** : 'configmap'
**-metadata/name** : an arbitrary name
**-data** : The actual contexts key-value pairs

### Secret Configuration File
**-kind** : "Secret"
**-metadata/name** : an arbitrary name
**-type** : "opaque" - default for arbitrary
> Deployment and service in one file because they belong together

### Deployment Configuration File
**-kind** : "Deployment"
**-template** : Configuration for pod has its own "metadata" and "spec" section
		**-Container** : Which image..? and which port...?
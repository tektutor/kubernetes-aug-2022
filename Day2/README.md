# Day 2 - Kubernetes

## Orchestration Platform
- a tool that helps us manage containers
- it offers the below features
    - in built monitoring features to check the health of our microservice Pods and heal them when required
    - supports scale up/down microservice instances on demand
    - supports upgrading/downgrading your microservices/applications in the live environment without any downtime
    - supports load balancing
    - supports service discovery ( i.e accessing the services by its name )
- Examples
   - Docker SWARM
       - this only supports managing Docker Containers
       - good for prototyping, learning, dev/qa setup
       - not production grade, hence rarely used in production
   - Google Kubernetes (K8s)
       - supports many different types of Container Runtimes/Engines
       - time test, production grade orchestration platform
       - unlike Docker, where every container is assigned an IP Address, in Kubernetes IP address is assigned on Pod level
       - supports many different inbuilt resources
            - Pod
            - ReplicaSet
            - Deployment ( you can deploy your applications as Deployment )
            - Service
                - Internal Service ( ClusterIP )
                - External Service ( NodePort & LoadBalancer )
            - Job
            - CronJob
            - StatefulSet
            - DaemonSet
     
## What is a Pod?
- Pod is Kubernetes resource
- Pod - a group of related containers
- Kubernetes/OpenShift manages application on the Pod level( not on the container level )
- all container that are part of a Pod, they share the IP address of the Pod

## What is a ReplicaSet?
- ReplicaSet supports scaling up/down your application/microservice on demand
- ReplicaSet is created by the Deployment ( Deployment Controller to be precise )
- ReplicaSet manages the Pod(s)

## What is a Deployment?
- user applications are deployed into Kubernetes as Deployment
- When we create a deployment, we generally 
     - give a name for the deployment
     - request minimum number of microservice/app instances that should be created/running
     - the container image that should be used to create the Pod
- Deployment Creation involves
    - Deployment 
    - ReplicaSet and
    - Pod(s)
- Deployment has one ReplicaSet per version of your microservice/application
- Deployment has one or more ReplicaSet(s)
- Deployment supports Rolling update
   - upgrading/downgrading your live application without downtime from Kubernetes
    
 

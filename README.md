# High Availability (HA)
- is difficult or expensive in case of Monothilic applications
- they are cheaper in case of Microservice applications

# Monolithic application
- Traditional application generally follow this architecture
- 3 tier applications
    - Frontend layer
    - Business layer
    - DB Layer
- Scale up/down
   is expensive
- several components
  Web Server / App Server
     - Server 1
     - Monolithic application is deployed here
  DB Server
     - Server 2
  Message Queue
     - Server 3


# RDBMS
- supports ACID Properties by default

# NoSQL Databases
- they don't support ACID property

# Microservice Overview
- self-contained, independent application that solves/focuses one functionality
- distributed computed
- NoSQL DBs
  - Mongo DB
  - CouchBase 


# Virtualization
- is called as Hypevisor
- with this we can run many Operating Systems side by side on the same Desktop/Laptop/Workstation/Server
- VMWare
    - workstation ( Windows, Linux & Mac )
    - Fusion ( Mac)
    - vSpehere (v-center) - Bare Metal Hypervisor
- heavy weight virtualization
    - each virtual machine( Guest OS) requires dedicated hardware resources
       - they need dedicated CPU, RAM and storage

# Docker Overview
- a container technology
- developed by Docker Inc organization
- comes in two flavour
   - Community Edition ( opensource )
   - Enterprise Edition (Paid)
- an application virtualization technology
- container is not a OS
- containers are nothing but application process that runs in a separe namespace(virtual sandbox environment)
- container is not a virtual machine
- within a Virtual Machine, we can install Docker or similar container tools 

# Orchestration Platform Overview
- container management platform
- examples
  - Docker SWARM ( supports only Dockerized based applications )
  - Google Kubernetes ( opensource )
  - RedHat OpenShift

- features offered
   - inbuilt application monitoring
   - High Availability
   - self healing
   - Scaling up/down
   - rolling update
       - upgrating your live application from one version to other without downtime
   - load balancing
   - service discovery
- Operators
   - You have ready-made or you can create custom operators that can create a cluster of DB Servers that can synchronize data


RedHat OpenShift
- RedHat's distribution of Kubernetes with many additional features
- is not just an orchestration platform
- it also supports CI/CD
- TekTon serverless CI/CD (Continuous Integration/Continuous Delivery/Continuous Deployment) pipeline
- kube-virt you can also scale up/down additional nodes(servers - virtual machine)


Microservice
 - NodeJS application with Postgres Database
 - one pod that runs NodeJS application
 - another pod that runs Postgres Database
 - put togeteher nodejs Pod ( NodeJS appl)  + Postgres Pod (DB) => Single Microservice ( multi-pod microservice )


# Agile
  - a concept , a way of working which helps you get frequent feedback from customer
  - SCRUM/Kanban/XP is an Agile Framework
  - alternate to waterfall framework
  - fail-fast software development approach that helps us in getting frequent feedback from customer

# DevOps
- automated process to build, test and release the product to customer with confidence
- Organization that follow SCRUM or any Agile Framework like Kanban will follow DevOps as their engineering practice
- DevOps Tools
  Version Control Softwares ( Source Control)
    - Git/GitHub
    - Perforce
    - Clear Case
  Build tools
    - Make
    - Ant, Maven/Gradle
  Containerization
    - Docker
    - Podman
  Orchestration Platforms
    - Google Kubernetes
    - RedHat OpenShift
    - Docker Sward
  CI/CD Servers
    - Jenkins
    - Bamboo
    - TeamCity
    - Microsoft TFS(TEam Foundation Server)
    
    
# Hypervisor
- refers to Virtualization technology
- Vendor specific Hypervisor tools
  Redhat
    - kvm (Kernel Virtual Machine) - Type 2
    - free for personal & commercial use
    - extremely efficient in terms of Performace as it is tightly integrated with Kernel
  VMWare
     - vSphere - Commercial Product ( Type 1 )
     - Workstation (Linux,Windows & Mac) - Commercial Product (Type 2 )
     - Fusion(Mac) - Paid software (Type 2)
  Microsoft
     - Hyper-V ( Microsoft Windows Pro 10 & all latest Server grade OS )
  Oracle
     - VirtualBox ( Free, works in Windows, Linux and Mac )
  Parallels(Mac)
     - Paid software
- comes in two flavors
  1. Type 1 (Bare Metal Hypervisors - Used in Servers/Workstations )
  2. Type 2 (Used in Laptops/Desktops/Workstations )


## Containers
- application process
- one application per container is the recommended practice
- typically also supports shell prompt ( bash or sh, etc )
- each container get's an IP address 
- each container has a file system
- each container has a separate copy of Network Stack ( 7 OSI Layers )
    - hence every container has a software defined network card
- doesn't have its own OS kernel as it is not an Operating System

Different Linux OS Distributions and Package Managers supports
- Ubuntu Linux Distribution
    - it supports a package manager called apt(apt-get)
-  RedHat CentOS/RHEL Linux Distribution
    - it supports a package manager called yum or rpm

# Container Image
- is a blueprint of a container
- using a single Container Image, one can create any number of containers
- software tools can be installed in an Image, when containers are created it will
  have all the software that are pre-installed in the image
- this is similar to VMWare image or iso 
- except that it is not a OS image
- has some package manager
  - helps in installing/uninstalling/upgrading software within a Linux distribution

# Container
- is an running instance of the Container Image
- get's it own IP address, shell, package manager and file system
- typically has the application and its dependent libraries


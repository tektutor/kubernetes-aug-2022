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

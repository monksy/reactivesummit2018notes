# Akka Cluster vs Kubernettes

----

 - Fabio - @ticofab
 - Adam Sandor - @adamsand0r

## Reactive community vs kubernettes community

 - Middle meeting - Reactive Distriubted Systems
   - Akka : Implementation
   - Kubernetetes: Distrubtions

## Questions

 1. Can kubernetes make an reactive application?


## What is resilience
  
  - Fault toleerence - Component is being hit but keeps going - possibly wiht reduced functionality
  - Resilience - Upon failure a component is able to reset into functional state
  
## Akka 

  - Reactive principles -> Reactive design patterns - Reactive building blocks [jvm/application level]
   - Actors gossip to each other about what/who they are
  - Supervisor can handle situations
  
## Kubernettes

  - Container orchestration engine at heart 
   - Has rules for what services have to be up 
  - Reactive?
    - Service abstraction + load balencing
    - Simple processing requests
  - Pipelines?
  
  
## Akka
  - Statemeful microservice architecture
  
## Stateless
  - Sends state to a persistent store
  
  
## Is akka cluster suitable for a microservice architecture?

Are actors microservices?

Yes 

Actor in akka cluster & microservice on kubernettes

They all have location transparency, resilency, scalability

But they're not independently deployable.

### One codebase - one cluster 

 - All code is in one cluster   
 - Cluster per pod

### Actually seperate the code bases 
  
  - Put them all in one akka cluster (communication between pods)
  - Mulitple webservice gateways

### Seperate codebase/seperate clusters

  - Seperate services via clusters
  

## How can Akka Cluster and Kubernetes Work Together?

 - K8s creates nodes and help form cluster?
   - Membership
 - Akka Bootstrap (cluster registration)

## Kubernettes resilency
 
 - Pod restarts based on healthchecks 
   - System level 
    -Can catch non expected cases    

## Questions

 1. How does kubernettes handle processing requests that require state?
 2. Processing/clustering management vs akka
 3. Auto scaling akka clustering based on demand? 
 4. How do you deploy new code bases to clusters (Managmenet of new code deployments/reprocessing)
   4.5 Api management /akka cluster membership
 5. Scaling down


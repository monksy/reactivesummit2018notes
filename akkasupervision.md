# Akka Supervision Strategies 

-----

Speaker: 
Twitter: 

-----


## Background

 - Gossip: Can get information about a node being down
 - Leader determines membership
    - What happens on routing of messages? 
 
## Make and order 

 - Send order to restaruant 
   - Returns estimations
 - Stateful akka actor 
 
## Recovery Points
 
  - Persist the state in storage
    - Inlcude time of task, status, meta, and host of node
  - Leader: Gets notified about nodes go down 
    - Must query database 
  - Recovery


## Recovery Node Goes Down

  - Leader initiates a recovery 
     - Work is redistributed
  - Leader is killed 
  - Functionality to find orphaned

## Leader Node Goes Down 

  - Recovery timer && Leader goes down 
    - Restart recovery time started on all active nodes 
  - New Leader
     - Reinitiate recovery of "recovery node"
  - 


------

All should be handled by cluster sharding
https://doc.akka.io/docs/akka/2.5/cluster-sharding.html

https://manuel.bernhardt.io/2018/02/26/tour-akka-cluster-cluster-sharding/
  
----

## Questions

  1. Actors per nodes (creating new actors per order)
  2. If an actor is marked as being down and sends a message later .. 
     2. how is that message handled?
  3. How do you determine failure or just takes too long?
  4. Persistent storage: Does the collapse/compat orders?
  5. Does this work with the akka finite state machine?

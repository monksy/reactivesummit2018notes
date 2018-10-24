# Distributed Data and Clustering 

-----

Author: ?
Twitter: paltaie

-----

## Akka Clustering 

 - Gossip based 
 - Decentralised

## Considerations

 - State maintence 

## Cluster Singleton 

 - Runs on the oldest node on the cluster 
 - Any actor can be a cluster singleton
 - Akka ensures only one instance of it runs on the cluster

 ## Distributed Data

  - Fancy eventually consistent distriuted store
  - Replicator actor 
  - CRDTs solve conflict problems 
  - CRDT 
     - G- Grow
     - PN - Positive Negative - Can increase and decrease in size
     - Oserved Remove Set 
     - LWW - Last Writter wins
  - Special collections that resolve in conflicts


## Demo Write a TFTP Server

 - Subset of FTP 
 - Lock step protocol 
 - Requirement: resilient, distributed


## Notes

 - DD not blazingly fast
 - Replication gets slower
 - Akka DD Not for big data

## Insterating bits

 - ClusterSingletonManager
 - Akka can bind it's self to a port and recieve messages
 - Max limit 100k top level elements across the cluster.

The demo hands over the cluster singleton. (That's pretty cool!)

----

Documentation: 
https://doc.akka.io/docs/akka/2.5.4/scala/distributed-data.html
https://github.com/paltaie/akka-tftp-server

---
  
  Todo; Get demo code
  

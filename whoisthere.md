# Akka Clusters
-------

Speaker: Manuel Bernhardt 
Twitter: @elmanu


# Issues
 
  - Discovery- WHo is there
  - Fault detection- who is in trouble
  - Load Balencing - Who can take up the work
    - Group membership
    - Consuss

## Failure Detection

  - Failure detector key properties
    - Completeness - Creash failure of any group member is detected by all non-faulty members
    - Accuracy- No non-faluty group member is declared as failed by any other non-faulty group 
    member ( no false positives

  - Considerations: Speed + network message load

## Impossibility result

It is impossible for a failuture dector algorithm to achieve both compleness, [missing]

Strong/Weak completeness - all/some non-faulty members detect a cash

Strong/weak accuracy - no /some false posisitves

- Most applications prefer strong completeness with a weakrer form of accuracy

## Strategies

 - Health checks: heart beats /ping : no/bad response = failure
 - Phi Adaptive Accrual Failture Detector
    - Adaptive: Adjusts to network conditions
    - Accural failure detection- can be more tolerent upon busy systems
    - Detection backs off exponentially
    - Qutntifies failures and can have different resolution strategies
    - Made popular by cassandra
  - New Adaptive Accural failure detective 
    - "More adaptive" 
  - SWIM Failure Detector
    - Disseminatino and failure detection component
    - Scalable membership protocol
    - Members are first suspected and not immediately flagged as failure 
      - Ping from one node to another, fails? Asks others to ping the node that failed
    - False positives
  - Lifeguard Failure Detector
    - Reduces false positives of Lifeguard Failure Detctor

 ## Dissemination

   - Membership
     - Joining, leaving, failing
   - Strategies
     - Multicast
     - Gossip protocols
       - Based on P2P networks
       - Random gossip - pick one other random node
        - Spreds fast
       - Round Robin gossip - determines waht will get next
       - Binary Round Robn 
       - Round robin with sequence check
       - Infection style gosip- SWIM with information
    - What do you gossip about
       - Results 
       - Failure detection
    - Gossip optimizations
     - Akka cluster 
       - gossip with a higherprobability to nodes that have not seen a gossip
       - Speeds up gossip when less than half of the members have seen the latest gossip
     - Lifeguard - determines when a full refresh is needed 

## Consesus 

 - Consensus timeline: Paxos, raft, consensus is that computers terrible (@ShlomiNoach)
 - Group membership 
   - Single group - Unwise to continue with work with a node that is suspected as crashed 
   [unconfident decisions] 
 - Lamport Clocks - How do you order events in a distributed system (L. Lamport: Time, clocks, 
 and the order of events)
 - Vector clocks- How do you order events in a distributed system and flag concurrent events)
 - Version vectors/ Dotted Version vectors - Similar semantics, primarily concerned with 
 versioning and conflict detction in replicas.

Akka clustering's gossip: https://gist.github.com/jboner/7692270

## Reaching consensus - replicated state machines 

  - Protocols (Agree on one single value)
    - PAXOS
    - Raft
    - Flexible Paxos
    - CASPaxos
    - Fast Paxos
  - Conflict Free Replicated Data Types
   - Strong eventual consistency
   - 2 Families 
     - CmRDTs - Commutativity of operations
     - CvRDTs - Convergence of state (merge function)

## Akka cluster 
 - Failure detector phi adapive accural FD with ping pong 
 - Dissemination - Random biased gossip 
 - COnsensus - Leader by convention
   - Membership decisions drive by leader (joining, leaving) 

## Where do we go from here?

  - Everyone is asking if: Is anyone out there?
  - 
-----

## Questions

1. What kind of problems is this trying to solve?
2. Is the consesus built and routting determined by the application structure? (Tasks that have 
dependencies)

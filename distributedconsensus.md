# Distributed Consesus

Speaker: Heidi Howard
Twitter: @heidiann360

Find slides: Speaker too quick
Summary: https://www.reactivesummit.org/2018/schedule/liberating-distributed-consensus

## Prior

 - Impossiblity of Dsitributed consensus with one faulty process
 - A hundred impossiblity proofs for distributed computing

## Deciding a single value 

  - Servers - store the value
  - Clients which read/write the value
  - Assume unreliable async, non-byzantine system

## Current
  
 - Classic paxos- majority based for reaching consensus
 - Mulit paxos - Local run electections with majority rule 
    - Leader Run (different strategies 

## Current opinion on paxos

 - Rarely understood

### Limitations
 

 - Distrubtion is limited 
   - Performance is bad 
   - Multipaxos 
      - Leader is bottleneck
   - Classic paxos - 2 round trips needed to reach consesnus


## Abstact solution to consensus using immutable state

  - Immuatable table (what each server state claims and what their value was for a data) 

  | s0 | s1 | s2 
------------------
1 | v1 |   |  
2 |    | v2 | v2

Left col is epoch (time)

### Decision point 

When there have been enough values and a qurum can be reached.

Prior example, quarum is reached when the majority has been passed. 

Decisions can be changed is mulitple majorites have been made. 

Multiple values can be reached if there are ties. 

Needs a rule on when values can be reached

### Safety 

Only one value should ever be decided

 1. No other values are decided for epoch 2
 2. ???

### Epoch allocation rule

   - Exclusive value - requires only one value will be written to each epoch 
   - Non-execusive valu allows any value to written to any epoch ... requires qarums. ?? 

### Client state 

  - Each client stores a copy of the state table
   - Clients can read values from any register
   - Clients can write nil values to any register
  - Client can track decisions
   - Client learns that value v has been decided then the client can return v?


## Classical to prove that it's conservative

 -  Epochs are exclusive and allocated round robin to clients. Use majority for quarms 
 - Choose an epoch to all servers
 - Provided register e is unwritten each server writes nil in unwritten registers 
 - After a majority of servers reply client chooses value v with greatest epoch or each value 
if none 
 - Client provises a new value to servers 

### Quorum intersection

 - Original requirement - Paxos requires that each of its two phaes use a quorum of servers and 
that any two quriousms must interect 
 - Revised requirement - A client in epoch e must get at least one server to

### Early completion of reading phase 

### Value selection

  - Original requirement - Paxos requires that the value with the great epcoh is provised in 
phased two .. No values were [missed]
  - Revised requirement - [missed] 

## Sketch 3 new algorithms made possible by abstaction

 - Co-located consensus 
  - Goal in colated ssytem - quicker to make agreement
 - Supermajority consesnsus
   - Allow any client to decide a value  ( missed rest)
   - Needs 4/5 servers are up and no colusions occur 
   - Con - 2 rtts are needed if 2 or more servers are slow/unavialble or a colision occures
   - Clients proposiing the same value do not collide

 - Binary consesus - Binar decision algorithm in which any client can decide [missed]
    - cons: Clients propising value 1 need 2 rtts to compete [assumed 0] 
     - only works for reaching a consensus over binary
    - pro- clients proposiing the same value do not colide

## Summary 
 - Safety - immutable is safe and tracking
 - Flexibility - choose own strategy 

## Closing Remarks 
 
 Paxos is a single point on a broad and diverse spectrum of consensus algorithms. 

## Question

 1. Why do we need to worry about distributed consensus, what are some applications of this? 
 2. Is this for dealing with probablitist partical results?

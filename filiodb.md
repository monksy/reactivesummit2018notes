# FilioDB

## What is it

## Challenges

  - Lots of writes 
    - Arch change 
  - GC issues 
    - Moved to serialization alternatives BinaryRecord that were off heap 
    
## Alternatives
 
  * Promethus is single node only (Filio has nodes)
  * FiloDB multischema and mltitenent
  * Influx
    - inlfux isn't open source 
  * Cassandra - much higher storage density and ingestion throughput for time series
    - Doesn't handle complex queries

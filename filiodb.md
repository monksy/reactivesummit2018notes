# FilioDB

Evan Chan: Twitter: ? 

## What is it

http://github.com/filodb/FiloDB

  - Meant for storing metrics with different schemas and multi-tenant
  - Promethus compatable
  - Time series storage 


## Prior Work

  - Faceook gorilla: Optimizes most recent data
  - Delta Difference - Line fits the data and stores deltas
  
## Encoding 
 - Columular storage for efficent storing 
  - Easier to pattern match for efficeint storage
  

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
  * Druid -olap 
     - Druid stores rollups 
       - Only stores processed data 
  
## Tradeoffs and lessons
  
  * Toolkit Pulses (See link) libraries for building distrubted and data systems
  * Apache Lucene (Ask why)
  * Akka Cluster 
  * Apple has to write a lot of libraries for raw memory manipulation

## JVM Production tips

 * Get to know your GCs very well (Eden, old gen, g1gc, )
 * [SJK] (http://github.com/aragozin/jvm-tools) - Analyize heaps
 * Runtime Visiblity (kamon)
   - Multiple apis to access cluster state
   - JMXBeans
 * Measure measure measure (Use JMH)

## Road map
 - Histogram optimization
 (Missed slide) 


-----

INvestigate later 

  - ConcurrentSkipListMap

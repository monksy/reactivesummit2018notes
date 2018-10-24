# Chaso Engineering

Twitter: ana_m_medina


## Suggestions

 * Add in monitoring first to determine a base line and a difference
 * Ramp up the tests from 1% all the way to 10%
 * Test, look for failure, escalate

## Levels

### 0: Chaos Monkey 

Software outages

### 1: Infrastructure levels


### 1.5 Network failures

#### Value provided

Prepare for high impact events 

### 2 Application Failures 

Safely validate the user experience 

## Layers to inject it into the stack

 * Application
 * Api
 * Caching 
 * Database
 * Hardware 
 * Cloud infrastructure/bare metal

## Tools

 * https://github.com/dastergon/awesome-chaos-engineering
 * Chaos Monkey https://github.com/Netflix/chaosmonkey
 * Kafka Breaks - 
 * Kube-moneky https://github.com/asobti/kube-monkey
 * Simian Monkey (instance failures)
 * Litmus - kubernettes 
 * Powerful seal - kubernettes
 *  

## Getting Started

 * Id top 5 critical systems
 * Choose system
 * Whiteboard the system
 * Determine what experiment you want to run (resource, state, network)
 * Determine blast radius 

## Chaos Days 

 * Group goal to break things and document
 * Days dedicated to focus on building resilience instead of new products

## Experiments to run

 * Reproduce outage conditions
 * Unpredictable circumstances
 * Large traffic spikes
 * Race conditions
 * Datacenter failure
 * Time travel (system clocks to be out of sync)
 * Network errors 
 * CPU Overloads

http://gremlin.com/chaos-monkey

http://bit.ly/chaos-eng-slack

## Questions 

 1. Have you done this with automated testing?
   - One company that can do.. Not a lot of people 

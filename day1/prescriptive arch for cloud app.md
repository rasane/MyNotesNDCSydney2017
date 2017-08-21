@MaheshKrishnan
Mail@mahe.sh

Prescriptive arch guidance for cloud applications

works for AGL 

going for breadh 
Patterns apply cloud/on premise

= > decouple components
= > design for elastic cloud

= > resilience
= > = > downstream services
= > = > eliminnate single points of failure
= > = >  degrade gracefully
= > = > failure is imminent

Continuous delivery
= > automate everything
= > Monitor
= > Self healing

build for perf/responsiveness
= >  do async
= > optimize for speed, not space (*) , consider if there is space for changing old design patterns
= > allow for latency

not born in cloud
= > need to work with legacy apps


Pttern categories
= >  availability patterns
= > data mgmt patterns
= > design and impl patterns
= > perf and scalability patterns
= > resiliency pattern


Availability pattern
= > health endpoint monitoring
= > = > problem: need to ensure that appp run with required SLAs
= > = > solution: create functionality within the applns to monitor health and report status, monitor health and report status, frequency of checking health, security for these endpoints, monitoring the monitoring system
= > = > 
= > load levelling
= > = > problem: performing long running operation that blocks the appln, intermittent heavy loads
= > = > Queues pattern: push requests in to a queue - can be combined with CQRS - idempotency of the operation
= > throttling
= > = > problem: intermittent heavy loads, causing system failure
= > = > add throttling. Monitor and reject certain high volume requests
= > = > consideration: this should be a temp measure and consider auto scaling , return appropriate error codes for rejected requests


Data mgmt patterns
= > Cache aside
= > = > caches help with performance & resiliency - but creates data consistency problems
= > = > load data from cache, when data is updated, invalidate corresponding item in cache
= > = > consider: lifetime of data, priming cache, data eviction policies, external process updating data source

= > Materialized view
= > = > problem reads tend to be slow and data not shaped or sized appropriately
= > = > soln : create separate views based on specific queries. combine calculated
= > = > consider: storage cost blow outs, trigger mechanism updating view, when data changes rapidly


= >  CQRS  - command query responsibility segregation
= > = > problem - mismatch between read and write, data contention 
= > = > soln: use a materialized viwe for reading and a queue for commands
= > = > consider: eventual consistency issues

= > Valet key pattern
= > = > problem: data transfer between client apps and data store results in compute, resources and bandwidth usage as it goes via cloud applns
<did not get this!!>


static content hosting pattern
= > = > prblm: static content html, js, css takes unnecessary load on server
= > = > soln: serve content from storage service rather than web server
= > = > consider: CDNs, security

Sharding pattern
= > problem: large data store, has limitations w.r.t storage space, n/w and computing bandwidth issues
= > solution: split in to horizontal partitions or shards, balance workloads across the shards
= > consider: sharding strategy avoid queries that span multiple shards, reference data replicated across all shards


design and implementation patterhns
= > ambassador pattern
= > = > problem: legacy appln talks to coud , consider adding NFRs to include resiliency and cater for nfr
= > anti corruption layer
= > = >  problem: communicating with legacy applications. bad downstream datastructures/apis make the cloud application go bad
= > = > solution: insert a layer to talk to legacy api.. new apps not affected
= > = > 
= > Backend for frontends
= > = > backend services tend to be very genericand different front ends (web, mobile etc. ) they are not fit for purpose
= > = > solution: create a separate backend for each and every frontend
= > = >  look out for code duplication
= > circuit breaker pattern
= > = > problem: failures, transient errors (fixed by retries..) but some errors last longer, blocked requests and retries chew up resources and cascading failures
= > = > circuit breaker gets triggered when repeated failures occur, it may have open, close and half open state to ensure that circuit can be reopened
= > = > consider: combine with health endpoint, consider alternate path flows consider accelerated circuit breaking

Gateway aggregation pattern
= >  problem: an app that makes several calls to get some functionality, this leads to chattiness, poor performance, overuse of resources
= >  solution: create a gateway that has to call the downstream services
= > consider: aggregation gateway should sit lcose to the backend, not the frontend. it could become a bottleneck

gateway routing pattern
= > problem: a client consumes a large set of services, setting up separate endpoints for each service can be challenging
= > solution: place a gateway in front of the services, similar to above , except affinity to client, rather than backend

Sidecar (orsidekick) pattern
= > problem: shared cross cutting pattern, like monitoring, logging configuration etc. when included
= > implement common services as a oop service that other languages / implementations can call
= > 

Strangler pattern
= > kill the legacy app by putting up a strangler facade until functionality in legacy apps 



Performance and scalability patterns
= > cache aside, CQRS, load levelling

Resiliency pattern
= > bulkhead
= > = > problem: single cloud appln that has multiple services, when one of thm fails it affects other hosted services
= > = > soln: use the bulkhead concept of ships where a leak in one close off that bulkhead, partition service instances in to groups or bulkheads. failure and excessive load on one won't affect others
= > = > consider: design bulkheads baed on business, tech requirements, isolate critical customer functionality

compensating transaction pattern
problem: when a action has to update multiple things in the backend, and one of them fails.. in the past there was a transaction, but when you are doing distributed applns transactions not useful/heavy
solution: provide a undo solution to the possible failure condition, error management
issue: 


scheduler agent supervisor pattern
porblme: when a number of steps define a work of an application, failure or success is a sum of all actions
solution: scheduler arranges steps and orchestration, agent contains logic for each step, supervisor monitors tasks done by scheduler and supervisor calls appropriate 
consider: difficult to follow through..
 



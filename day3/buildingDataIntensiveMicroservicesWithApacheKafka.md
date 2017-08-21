Building Data Intensive Microservices with Apache Kafka
@couchbase

Yaniv Rodenski


- no dependencies, scalable
lots of services, v1 are clean
then new requirements come in
which need us to use existing services and push data to other data stores


now tthe services are no longer autonomous and dependent on each other

databases are not integration points, they are for indexing, searching etc.
- implicit dependencies between services will lead to errors in mutable data

what if we pushed data through a stream and shared it on there

Apache Kafka
- LinkedIn created in 2010 - out of there similar needs
- pub/sub messaging, distributed tx log
- commercially supported 

- producers write topics - messages are written to data streams
- topics ar emade of transaction logs
- Partitions

-Producers
- write directly to a partition

Consumers
- do a lot of heavy lifting,
- kafka does not care about where the consumer is at in reading
- messages are stored as indexed in a array
- consumers batch process the data and consume it


advanced powerful consumers
- library called kafka streams - brings stream processing framework
- apache flink, spark streaming - needs a server - which is great but should not be necessary for a microservices architecture
- Kafka streaming brings this to the table
- KStream , creating a flatMap => creates a stream/array 

Steam table duality
=> KTable api
- is a table representation of the stream data.. e.g. stream of events, leads to a current set of values 


Kafka Connect
- moving data from 1 datastore to another - data integration, scalable, fault toleratnt, central management
- list of available connectors, can be easily created for new data sources 
- connect connects connectors ( source datastores ) to destination (sinks)

AVRO serialization format following the schema registry
- schema management/store

MirrorMaker - Kafka to kafka replication
    - open source, but no security control on the platform that the Confluent platofrm allows


for authentication/authorization = either pass it as part of the topic message itself or create a separate topic for this call context 
Microsoft Azure, HD Insight can support a Kafka services


Apache Nifi
- competing with Apache connect
- Nifi is a generic connect replacement where Kafka is one of the destination
- it 


Ktable - snapshoting
- using the indexes 


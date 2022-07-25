# Pulsar 

https://blog.rockthejvm.com/event-streaming-with-pulsar-and-scala/
https://blog.rockthejvm.com/pulsar-spark/
https://github.com/rockthejvm/spark-streaming
https://github.com/rockthejvm/udemy-spark-streaming
https://www.slideshare.net/databricks/apache-pulsar-the-next-generation-messaging-and-queuing-system
docker run -it \
  -p 6650:6650 \
  -p 8080:8080 \
  --name pulsar \
  apachepulsar/pulsar:2.8.0 \
  bin/pulsar standalone
  

docker exec -it pulsar bash
cd bin/
./pulsar-admin topics create events
docker run -it -p 6650:6650 -p 8080:8080 --name pulsar apachepulsar/pulsar:2.8.0 bin/pulsar standalone


==========
Apache Pulsar is a cloud Native Messaging and Event Streaming Platform

# 3 Key Components 
1. Pulsar PubSub
2. Pulsar Functions (LightWeight Compute With Pulsar Functions) Like Lambda
   Example : Source Topic ---> f(x) ---> Sink Topic 
3. Pulsar SQL (Presto)[Can join with data from other Sources ]

4. Pulsar IO :(Connectors Framework based on Pulsar Functions)
Pulsar Nodes 

ZookKeeepr

BOOK Keeper

Tiered Storage : New message --> Book Keeper --> S3 ---> GLACIER 

Pulsar SQL 

================
Producer Producer --> Topics
================
Pulsar Cluster ---> 
Tenants ---> Sales ,Marketing,Product 
Namespaces --> Microservices,ETL,Campagngs
Topics 
================
Messaging : Message passing between components,application services
Streaming --> Analayze events that just happended

Storage   :
Messaging :
Compute   :

Apache Pulsar : Flexiable Pubsub and Compute backed by durable log storage 
Durablity : Data Replicated and syn to disk 
Low Latency : Low publish latency of 5 ms at 99pct
High Througput : Can reach 1.8 M messages/s in a single partition 
Cloud Native : Take a advantage of dynamic cluster scaling in cloud enviornments

Unified Messgeing model :
High Scalable :
Native Compute :
Multi Tenants:
GeoLocation :



# Message Model 
1. Producer 1 --> pulsar Topic ---> Exec

Subscriptions types 
1. Execlusive
2. Failover 
3. Shared
4. Key_Shared 


# Why Pulsar?
https://www.techtarget.com/searchdatamanagement/post/Apache-Pulsar-vs-Kafka-and-other-data-processing-technologies

# partition (Kafka )
Apache Kafka is a partition-centric pub/sub system while Apache Pulsar is a segment-centric pub/sub system

# segment-centric(Apache Pulsar)


# Topics types 
persistent / non-persistent	This identifies the type of topic. Pulsar supports two kind of topics: persistent and non-persistent. The default is persistent, so if you do not specify a type, the topic is persistent. With persistent topics, all messages are durably persisted on disks (if the broker is not standalone, messages are durably persisted on multiple disks),
 whereas data for non-persistent topics is not persisted to storage disks.

# Pulsar Client Lib
Java --> C++,C,Python,Go,NodesJS WebSocket APIS
Apache Kafka Compatibility wrapper API 
Trasnparent batching and compression
TLS encryption and authencation
End to end encryption 

# Apache BookKeeper(Replicated Log Storage)
---> Low latecny durable writes
---> Simple Reperatble read consistency
--> High Avaiable 
---> Store 
Inside BookKeeper (Storage optimized for sequeicnal & immutable data)

Segment Centric Storage : In Addition to partitiong ,Messages are stored in segements(based on time and size)


# Schema Registry
*. Store Information on the data strcture -Stored in BookKeeper
*. Enforce data types on topic 
*. Allow for compatible schema evolutions

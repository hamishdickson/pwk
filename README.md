# playing with kafka

## some disorganised noob notes and definitions:

*def message*: unit of data - kafka treats these as an array of bytes. can have some metadata (key, also a byte array)

*def partition*: ??? (this is where you use a key). Typically, messages with the same key are written to the same partition

*def batch*: collection of messages

*def topics*: messages are catagorized into topics. These are normally broken down into partitions

messages are written to a partition in an append-only fashion. Read in order.

no guarentee of ordering in a topic, just within a single partition

each partition can be hosted on a different server

*def clients*: users of the system, two basic types, producers and consumers

*def producer*: create new messages

*def consumers*: read messages. keeps track of what messages have been consumed by keeping track of the offset of messages

*def offset*: bit of metadata an int which kafka adds to each message. each message in a partition has a unique offset. As a consumer you can store this in (say) zookeeper and know where you are in the partition

*def consumer group*: set of consumers which together consume a topic

*def broker*: single kafka server. designed to work as part of a cluster. One broker will be the controller (assigning partitions and monitoring for failures)

messages persist for some retention period (eg 7 days) or the topic reaches a certain size

*def mirror maker*: a tool used to copy the messages in kafka to another cluster.


## Zookeeper

Download at http://www.apache.org/dyn/closer.cgi/zookeeper/


## Kafka download

https://kafka.apache.org/downloads

Note: flink is on scala 2.11 at the moment

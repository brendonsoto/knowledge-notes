---
aliases: 
created: 2022-01-18, 10:21:46 am (Tuesday, January 18th)
updated: 2022-01-18, 10:29:16 am (Tuesday, January 18th)
---
High-level overview: servers and clients communicate via a TCP network protocol

## Servers
One or more servers form a **kafka cluster**.
Servers can be connected to different data centers and/or be located in different places.

The *storage layer*, also known as **brokers**, are formed from some of these servers.

[Kafka Connect](https://kafka.apache.org/documentation/#connect) is used to establish communication between Kafka and other systems (e.g. dbs, other clusters).

If a server fails, another will pick up the work.

## Clients
A client in Kafka-land is an interface that allows applications/services to communicate via event-streams.

## Questions
- What *exactly* is Kafka Connect for? Just between Kafka servers to DBs and other Clusters? How is it different than Clients?
    - Going by the [doc's Kafka's APIs](https://kafka.apache.org/documentation/#intro_apis), it looks like Connect is for directly connecting a db or other cluster, something that produces it's own stuff, not something you wrote, to kafka while Stream API is for providing the ability to interact with event streams

## Sources
---
aliases: 
created: 2022-01-18, 3:03:23 pm (Tuesday, January 18th)
updated: 2022-02-28, 8:01:26 am (Monday, February 28th)
---
ZooKeeper is an open-source server to help manage and coordinate distributed systems.

ZooKeeper operates kind of like a file system.
It all starts with a name space (`/`).
The name space holds "data registers", called **znodes**, which are kind of like files: they hold metadata.
They are identified via *paths* that are also separated by "/".
Every znode has a path whose parent is also a znode, but with one less element (like a file path).
Znodes with children cannot be deleted; there must be no children in order for a znode to be deleted.

The example diagram in the [docs](https://cwiki.apache.org/confluence/display/ZOOKEEPER/ProjectDescription) paints the picture of a zookeeper service holding data about other servers that clients can interface with.

The service is duplicated/replicated over multiple machines.
This group of machines *is* the service.
Data and logs are stored *in-memory*.
This is how ZooKeeper can get high throughput and low latency, potentially.

Servers in ZooKeeper must know about each other.
The ZooKeeper service will be available if a majority of its servers are available.

Clients connect to only one server via TCP.
On the initial connection, the server will make a session to have a record of talking with the client.
This is to help re-establish a connection between client and server if the initial connection breaks.

*Order* is *very important* to ZooKeeper.
The **zxid** (ZooKeeper Transaction ID) is a number assigned to updates to reflect the order of read and write operations.
## Sources
- https://zookeeper.apache.org/
- [Docs - Overview](https://cwiki.apache.org/confluence/display/ZOOKEEPER/ProjectDescription)
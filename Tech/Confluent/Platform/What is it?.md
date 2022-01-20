---
aliases: 
created: 2022-01-20, 9:10:16 am (Thursday, January 20th)
updated: 2022-01-20, 2:03:09 pm (Thursday, January 20th)
---
It's an event-streaming platform, basically [[Tech/Kafka/index|Kafka]] on steroids.

> Each release of Confluent Platform includes the latest release of Kafka and additional tools and services that make it easier to build and manage an Event Streaming Platform. Confluent Platform delivers both community and commercially licensed features that complement and enhance your Kafka deployment.

You can use it to set up an environment for storing, publishing, and subscribing to events/data, but with more tools like a GUI to manage streams/tables and the ability to manipulate the stream using a SQL-like syntax.

Pieces that can form it include:
- ZooKeeper -- manages the Kafka cluster
- Kafka brokers -- to store and relay events/data
- Kafka REST -- access the stream over HTTP instead of TCP
- Kafka Connect -- add data sources/sinks
- ksqlDB -- provides tooling that sits on top of Kafka to allow developers to interface with data in a SQL-like manner
- schema registry -- stores schemas and their changes with the goal of validating changes to protect against breaking the contract between producers and consumers
    - It makes me think of GraphQL's federation and API schemas. When you change the schema of an endpoint you have to be mindful of and update the client too or else things just won't work.
- Control Center -- GUI / Web App to interface with the Confluent tools
## Sources
- https://docs.confluent.io/platform/current/platform.html
---
aliases: 
created: 2022-01-20, 9:27:04 am (Thursday, January 20th)
updated: 2022-01-20, 1:25:12 pm (Thursday, January 20th)
---
See https://docs.confluent.io/platform/current/quickstart/ce-docker-quickstart.htm

They provide a docker compose file for setting up multiple containers running different applications.
From there, you can use their GUI via localhost:9021 to interact with the kafka cluster (add topics, connectors, query via ksqldb, and more).
Once you have a topic enabled and some events in it (or using data-gen component) you can read the stream using other tools like [[Tech/Kafka/How to/Read events|Kafka's console consumer script]]!


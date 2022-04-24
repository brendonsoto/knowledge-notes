---
aliases: 
created: 2022-01-18, 3:42:23 pm (Tuesday, January 18th)
updated: 2022-01-20, 3:53:03 pm (Thursday, January 20th)
---
This is to play with Kafka without any actual coding.

## Prerequisites
- Java

## Steps to run and play with events
- Download the Kafka archive file from Kafka's site
- Extract the files (i.e. unzip it)
- `cd` into the directory after extraction
- Start the zookeeper instance
    - `bin/zookeeper-server-start.sh config/zookeeper.properties`
- Open another terminal window
- Start the kafka broker
    - `bin/kafka-server-start.sh config/server.properties`
- Open another terminal window
- Create a topic
    - `bin/kafka-topics.sh --create --partitions 1 --replication-factor 1 --topic quickstart-events --bootstrap-server localhost:9092`
        - Replace `quickstart-events` with whatever you want to name your topic
- Start a producer
    - `bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092`
        - Same spiel as from creating a topic regarding `quickstart-events`
- Enter text and hit "Enter/Return" to send events (an event per line)
- Open another terminal window
- Start a consumer
    - `bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092`
- After a moment, you should see the events pop up
- At this point, switch back to the terminal with the producer, enter more text, and watch the events appear on the other side!

To stop, check out: [[Tech/Software/Kafka/How to/Stop a Kafka environment]]
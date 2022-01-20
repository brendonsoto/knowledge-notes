---
aliases: 
created: 2022-01-18, 10:33:14 am (Tuesday, January 18th)
updated: 2022-01-18, 10:58:32 am (Tuesday, January 18th)
---
- producers and consumers are fully decoupled and agnostic of each other

- regarding life-time of events, events can last forever or for however long you tell the event to remain for

- topics can have 0-n producers and consumers
- topics are **partitioned**
    - events with the same key belong to the same partition
    - this is for scalability? to write/read from/to multiple brokers at a time?
        - **QUESTION** I don't really get this. Why is it like this?
- topics can be **replicated** for fault-tolerance

## During the training
### Day 1
- something about K-streams
    - ksql db -- sql-like syntax (declarative) for k-stream applications
        - basically, for if you don't want to use Java
    - ksql being used synonymously with kafka something
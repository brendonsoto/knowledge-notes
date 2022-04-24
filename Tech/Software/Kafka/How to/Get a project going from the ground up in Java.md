---
aliases: 
created: 2022-01-18, 11:50:28 am (Tuesday, January 18th)
updated: 2022-01-18, 2:55:06 pm (Tuesday, January 18th)
---
## Prerequisites
- Java
- Maven

## Start
```java
mvn archetype:generate \
    -DarchetypeGroupId=org.apache.kafka \
    -DarchetypeArtifactId=streams-quickstart-java \
    -DarchetypeVersion=3.0.0 \
    -DgroupId=streams.examples \
    -DartifactId=streams.examples \
    -Dversion=0.1 \
    -Dpackage=myapps
```

I don't know much about Maven/Java so I'm guessing `groupId` or `artifactId` are what results in the directory structure.

This will produce examples in `src/main/java/myapps/` so you can delete them.

Write your code and when you're ready to run, [[Tech/Software/Kafka/How to/Start a kafka environment]], run your java app, and start up any necessary event producers or conumers.

## Related
- [[Tech/Software/Kafka/How to/Write an event]]
- [[Tech/Software/Kafka/How to/Read events]]
---
aliases: 
created: 2022-01-18, 10:58:46 am (Tuesday, January 18th)
updated: 2022-01-21, 10:47:55 am (Friday, January 21st)
---
`bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092`

**NOTE:** Kafka messages are *key/value* pairs.
Example message:
```JSON
{
    key: 1,
    value: {
    name: 'brendon',
    address: {
        city: 'New York'
    }
}
```

## Related
- [[Tech/Software/Kafka/How to/Read events]]
---
aliases: 
created: 2022-01-21, 9:53:00 am (Friday, January 21st)
updated: 2022-01-21, 10:03:37 am (Friday, January 21st)
---
- grab a Confluent API Key
- setup kafka as so:
```javascript
const { Kafka } = require("kafkajs");

const kafka = new Kafka({
    clientId: "test-app",
    brokers: ["name.to.broker.with:port"],
    ssl: true,
    sasl: {
        mechanism: "plain",
        username: "",
        password: "",
    },
 });
```

Now you can add your producers/consumers and you're all set!

## Related
- [[Tech/Confluent/How To/Create an API Key]]
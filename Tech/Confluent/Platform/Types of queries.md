---
aliases: 
created: 2022-01-20, 1:08:46 pm (Thursday, January 20th)
updated: 2022-01-20, 1:13:38 pm (Thursday, January 20th)
---
## Transient
- non-persistent
- client-side
- does not create a new topic
- can terminate either manually or with LIMIT clause

## Persistent
- server-side query
- outputs a new stream or table whose data comes from a new topic
- can terminate with a TERMINATE clause
- examples: `CREATE (STREAM|TABLE) AS SELECT`

## Push
- produces results continuosly to a subscription
- can be transient or persistent
- uses `EMIT CHANGES`

## Pull
- queries a table based on the current state, like a snapshot in time
- transient
- usually low latency (streams are always updated)
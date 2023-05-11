---
aliases: 
created: 2022-09-02, 2:46:36 pm (Friday, September 2nd)
updated: 2022-09-02, 5:35:58 pm (Friday, September 2nd)
---
WIP

Elasticsearch has **indices**, which is kind of like a database.


## What is Elasticsearch?
*Note: We're currently on version 7.17, hence the links to that version of the docs.*

From the [Elasticsearch guide](https://www.elastic.co/guide/en/elasticsearch/reference/7.17/elasticsearch-intro.html):
> Elasticsearch is a distributed document store. Instead of storing information as rows of columnar data, Elasticsearch stores complex data structures that have been serialized as JSON documents. When you have multiple Elasticsearch nodes in a cluster, stored documents are distributed across the cluster and can be accessed immediately from any node.

To me, that's a bit jargon heavy. I like to think of it as a different kind of database. We'll continue exploring Elasticsearch through comparing it to a database. Let's start at the beginning with creating a "database".

## Creating a "database"
You know how Postgres/MySQL/etc have different databases you can connect to and each has different *tables* with their own *schemas*? In Elasticsearch you have an **index**, which is kind of like a table. An index is where all of your data is stored but in an optimized way thanks to Elasticsearch's data structures. The idea of a schema in Elasticsearch is represented as a **mapping**.


---

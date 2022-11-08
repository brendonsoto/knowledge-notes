---
aliases: 
created: 2022-09-02, 11:19:28 am (Friday, September 2nd)
updated: 2022-09-02, 11:22:54 am (Friday, September 2nd)
---
Starting from [here](https://www.elastic.co/guide/en/elasticsearch/reference/current/documents-indices.html)...

> Elasticsearch is a distributed document store. Instead of storing information as rows of columnar data, Elasticsearch stores complex data structures that have been serialized as JSON documents. When you have multiple Elasticsearch nodes in a cluster, stored documents are distributed across the cluster and can be accessed immediately from any node.

So Elasticsearch is a tool for searching.
It stores information about files in JSON documents that represents specific Elasticsearch data structures (what do they look like? idk).
I guess one instance of Elasticsearch is a "node" and multiple can communicate with each other.

Going off of [the intro page](https://www.elastic.co/guide/en/elasticsearch/reference/current/elasticsearch-intro.html) Elasticsearch takes in data of any format and adds some data that somehow allows you to quickly search for the data.

So...
-> data goes into elasticsearch
-> elasticsearch takes that data and creates a JSON document in the shape of their data structure
-> this JSON doc is stored in elasticsearch
-> that JSON doc is "indexed"

pause, what does "index" mean?
From the [documents and indices page](https://www.elastic.co/guide/en/elasticsearch/reference/current/documents-indices.html):
> An index can be thought of as an optimized collection of documents and each document is a collection of fields, which are the key-value pairs that contain your data.

This makes me think of "indexing" as just re-organizing the collection of JSON documents to optimize searching.

Elasticsearch can work with schemas that describe the data you're providing.
Elasticsearch an also work without a schema.
In this case, Elasticsearch will look at your data, the types involved, and dynamically create schemas for it.
The same page outlines some benefits to making your own schema.

Okay.
Where does "mapping" come in?

From the [mapping doc page](https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping.html):
> Mapping is the process of defining how a document, and the fields it contains, are stored and indexed.

Okay, so "mapping" is a way to tell Elasticsearch how to store and index data.
Ah, this is the "schema" bit.
So a "mapping" is really a "schema".
There's *dynamic mapping* and *explicit mapping*.
These terms describe the act of either having Elasticsearch create schemas or you creating them yourself.

Okay
After a bit more googling around I have learned that hitting `localhost:<port>/<whatever>` shows you JSON representing the Index which consists of:
- aliases (alternative names)
- mappings (fields and their data types)
- settings

There's also `localhost:<port>/<whatever>/_mappings` which will return *just* the mappings, but you get that with the other URL too.
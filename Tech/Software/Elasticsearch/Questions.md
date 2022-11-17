---
aliases: 
created: 2022-08-26, 4:13:23 pm (Friday, August 26th)
updated: 2022-08-26, 4:18:22 pm (Friday, August 26th)
---
Dump space for stuff related to Elasticsearch cause I know I'm going to forget.

## What does a "schema" look like?
To see what a "schema looks like" from a running server and you know the name of an index (I guess the name of a schema?) use: `http://<url-of-elastic-search>/<index>`
For instance, you're running a local instance on port 5555 and want to find what fields are available on the instruments index, you'd hit
`http://localhost:5555/instruments`

[Source](https://www.elastic.co/guide/en/elasticsearch/reference/6.8/indices-get-index.html)

If you want to query a specific entity (like, find a specific record or records based on some field):
 `http://<url-of-elastic-search>/<index>/_search?q=<field-key>:<value>`
Using the above example again, if we wanted to find any stringed instruments (assume there's a "type" field) we can hit:
`http://localhost:5555/instruments/_search?q=type:stringed`

[Source](https://www.elastic.co/guide/en/elasticsearch/reference/6.8/search-uri-request.html)

## What's the DSL?
https://www.elastic.co/guide/en/elasticsearch/reference/6.8/query-dsl-match-all-query.html
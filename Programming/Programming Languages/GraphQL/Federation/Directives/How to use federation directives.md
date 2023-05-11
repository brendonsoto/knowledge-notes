---
aliases: 
created: 2022-03-24, 10:43:40 am (Thursday, March 24th)
updated: 2022-03-24, 10:45:07 am (Thursday, March 24th)
---
First, you'll need the code: https://www.apollographql.com/docs/federation/federation-spec/#federation-schema-specification

If using a tool like [graphql config](https://www.graphql-config.com/docs/user/user-introduction) you can do something like the following:

```yaml
schema:
  - src/schema.graphql
  - lib/federation-directives.graphql
documents: src/**/*.graphql
```
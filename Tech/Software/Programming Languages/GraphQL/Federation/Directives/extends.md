---
aliases: 
created: 2022-01-07, 1:17:57 pm (Friday, January 7th)
updated: 2022-03-24, 11:15:55 am (Thursday, March 24th)
---
#graphql #how-to #federation

Syntax: `@extends`
Example: #to-do

```graphql
extend type Tea @key(fields: "id") {
    id: ID! @external
}
```

The `@extends` directive allows you to add fields to a type from another graph.
It requires referencing the [[Tech/GraphQL/Federation/Directives/key|key directive]] from the main type through the [[Tech/GraphQL/Federation/Directives/external|external directive]]

## Related
- [[Tech/GraphQL/Federation/Directives/external]]
- [[Tech/GraphQL/Federation/Directives/key]]
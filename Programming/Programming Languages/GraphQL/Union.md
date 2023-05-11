---
aliases: 
created: 2021-12-09, 1:49:05 pm (Thursday, December 9th)
updated: 2022-01-10, 12:30:01 pm (Monday, January 10th)
---
#graphql #data-structures #types

# Union
[source](https://spec.graphql.org/June2018/#sec-Unions)

A union groups multiple object types as possibilities for one type.
It does *not* have any fields itself.
It communicates a type can be one of other types.

For example (from the spec):
```
union SearchResult = Photo | Person

type Person {
  name: String
  age: Int
}

type Photo {
  height: Int
  width: Int
}

type SearchQuery {
  firstSearchResult: SearchResult
}
```

So `SearchResult` can be *either* a `Photo` *or* a `Person`

## Related
- [[Programming/Programming Languages/GraphQL/Interface]]
- [[Programming/Programming Languages/GraphQL/Object]]
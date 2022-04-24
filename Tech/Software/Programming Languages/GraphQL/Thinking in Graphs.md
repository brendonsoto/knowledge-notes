---
aliases: 
created: 2021-12-22, 11:06:44 am (Wednesday, December 22nd)
updated: 2022-01-10, 12:32:17 pm (Monday, January 10th)
---
#graphql #data-structures

[Source - graphql best practices docs](https://graphql.org/learn/thinking-in-graphs/)

- the graph is just the *interface*
    - any backend can be used to *implement* the interface
- use the same language as your customers/business
- regarding working with legacy data:
    - > Prefer building a GraphQL schema that describes how clients use the data, rather than mirroring the legacy database schema.
- **don't** try to model the *entire* domain in one sitting; be iterative

## Related
- [[Tech/Software/Programming Languages/GraphQL/On Designing]]
- [[Tech/Software/Programming Languages/GraphQL/Pagination]]
- [[Tech/Software/DataStructures/Graph]]
- [[Tech/Software/DataStructures/GraphConnection]]
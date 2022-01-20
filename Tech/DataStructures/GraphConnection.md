---
aliases: 
created: 2021-12-07, 10:01:07 pm (Tuesday, December 7th)
updated: 2022-01-10, 12:29:02 pm (Monday, January 10th)
---
#data-structures #graphql

# Connection
[Source](https://relay.dev/graphql/connections.htm)

This is a data structure to traverse a graph
The naming convention is `<Thing>Connection`
Example using Pokemon Cards: `PokemonCardConnection`
- Note the *singular* use

## Structure
- PageInfo: Tells you if there's content before and after the current range alongside the start and end
- edges:
  - seems to communicate current position in the graph
- nodes:
  - seems to communicate all possibilities

  ## Related
  - [[Tech/DataStructures/Graph]]
  - [[Tech/Programming Languages/GraphQL/Pagination|cursor-based-pagination Connections-pattern]]
#data-structures #graphql

# Connection
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
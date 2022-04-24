---
aliases: cursor-based-pagination Connections-pattern
created: 2021-12-22, 11:11:57 am (Wednesday, December 22nd)
updated: 2022-01-10, 12:29:11 pm (Monday, January 10th)
---
#graphql #best-practices


## Connections pattern
Also described as cursor-based pagination.

Must have these types (can have others if the designer wants):
- `Edges`
- `PageInfo`

## Types
### Edge type
In the context of GraphQL and the Connections pattern an edge type is an [[Tech/Software/Programming Languages/GraphQL/Object]] that must have the following properties:
- `node`
- `cursor`

Conceptually...

#### Node type
A node is a wrapper around a value. Like a mailbox.

The object/value; the core content; can be any NonNull type that's *not* a list

#### Cursor type
A sort of ID for the *connection*, the edge, itself.

Why not just use the ID of the node?
Because we want to make sure this type signifies it's *only* a marker, nothing more, nothing less.

### PageInfo type
Must have:
- `hasPreviousPage`
- `hasNextPage`
- `startCursor`
- `endCursor`

## Arguments
Any `Connection` type must include arguments for either *forward* pagination or *backwards* pagination or *both*.

### Forward pagination
- `first`
    - non-negative integer
- `after`
    - [[Tech/Software/Programming Languages/GraphQL/Pagination#Cursor type|cursor]]

The idea is to get the `first` X edges `after` cursor A.

### Backwards pagination
- `last`
    - non-negative integer
- `before`
    - [[Tech/Software/Programming Languages/GraphQL/Pagination#Cursor type|cursor]]

You get the idea.

## Algorithm

## Questions
### how does graphql/a connection know where to start?
It depends.
What logic is being used to order the edges?
According to the [spec](https://relay.dev/graphql/connections.htm#sec-Edge-order) the way that edges are ordered does not matter. What *does* matter is making sure the system used to order edges is consistent.

So what does this really mean?

I like to think of it as a GraphQL resolver asking a DB for sorted data and then applying the pagination [[Tech/Software/Programming Languages/GraphQL/Pagination#Algorithm|algorithm]].

Let's think about it like this.
GraphQL uses resolvers to get data, right?
And that data can come from anywhere.
Let's say it's coming from in-memory, an array in the running program.
That array naturally has an order: the order items were added to it.
Thus when the algorithm is applied and edges are created the *node* becomes a value from the array and the *cursor* becomes some arbitrary ID

### what does it mean if a cursor is "opaque"?
Haven't been able to find a solid answer


## Sources
- https://graphql.org/learn/pagination/
- https://relay.dev/graphql/connections.htm
- https://www.youtube.com/watch?v=dCQ9g5V_CxE
    - I really liked this video. Nice and simple.
- https://jacobruiz.com/blog/2019/6/19/graphql-pagination-opaque-cursors
    - The code is way more helpful than the explanation
- https://www.youtube.com/watch?v=e1cbhZ5vDGc&t=180s
    - THIS!!!
    - This made the concept of cursor click for me. I got the idea that it's just a marker and the idea that it doesn't hold any "meaning", but I think it kind of does. The cursor helps identify where you are in a set of data. It also can be used for defining boundaries for the sub-set of the dataset you're working with. It's like a `Map` in JS; keys are cursors
- https://www.youtube.com/watch?v=WUICbOOtAic
    - this is a nice overview between offset and cursor-based pagination w/o GraphQL

    ## Related
    - [[Tech/Software/DataStructures/GraphConnection]]
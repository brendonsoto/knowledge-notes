---
aliases: 
created: 2022-01-07, 1:12:35 pm (Friday, January 7th)
updated: 2022-01-07, 1:24:36 pm (Friday, January 7th)
---
#graphql #federation

## key
Syntax: `@key`
Example: `type Product @key(fields: "uuid") { ...`

I have a bit of trouble explaining this.
Tells the federation the associated type is what should be used if other graphs want to extend it.
It's the authoritative type in the total/supergraph.

Consider you have a supergraph made up of two graphs.
Each has their own `Product` type.
Which one should be used as the main type?
That's where the `@key` directive comes in.

That's not to say other types can't extend it.

## Related
- [[Tech/Software/Programming Languages/GraphQL/Federation/Directives/extends]]
- [[Tech/Software/Programming Languages/GraphQL/Federation/Directives/external]]
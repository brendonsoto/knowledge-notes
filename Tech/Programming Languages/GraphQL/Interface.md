---
aliases: 
created: 2021-12-09, 11:44:16 am (Thursday, December 9th)
updated: 2022-01-10, 12:30:52 pm (Monday, January 10th)
---
#graphql #data-structures #types

# Interface
An **interface** is a grouping of fields and their types that other types may implement.
It's similar to Object Oriented Interfaces.
Use the `implements` keyword to use an interface.

## Examples
### Implementing an interface
```
interface Person {
  name: String
}

type Musician implements Person {
  name: String
  instrument: String
}

type Author implements Person {
  name: String
  genre: String
}
```

### Using an interface as a field
Re-using the Person example above
```
type Contact {
  person: Person
  number: String
}
```

Why?
So we can query on fields we know exist across any type that implements that interface
So we can write queries like
```
// Generic
{
  person {
    name
  }
}

// More specific
// Let's say we have a Contact like:
Contact {
  person: { ...Musician } // Some musician
  number: "123"
}

// The above query would still work since Musician implements Person
```

## Questions
### If an interface already has the types to be implemented, why do you have to re-write them in the implemented type?

## Quotes
From [the GraphQL Spec](https://spec.graphql.org/June2018/#sec-Interfaces)

> GraphQL interfaces represent a list of named fields and their arguments. GraphQL objects can then implement these interfaces which requires that the object type will define all fields defined by those interfaces.

> Fields which yield an interface are useful when one of many Object types are expected, but some fields should be guaranteed.

## Related
- [[Tech/Programming Languages/GraphQL/Union]]
- [[Tech/Programming Languages/GraphQL/Object]]
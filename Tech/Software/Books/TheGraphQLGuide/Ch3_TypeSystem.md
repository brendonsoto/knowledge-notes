---
aliases: 
created: 2022-02-28, 7:41:02 pm (Monday, February 28th)
updated: 2022-02-28, 8:11:55 pm (Monday, February 28th)
---
## Schema

I really like this definition:
> The schema defines the capabilities of a GraphQL server.

There are three **root fields:**
- `Query`
    - get data
- `Mutation`
    - add or update data
- `Subscription`
    - get constant access to data

## Types

There are *named* and *wrapping* types.

Named:
- `Scalar`
- `Enum`
- `Object`
- `Input object`
- `Interface`
- `Union`

Wrapping:
- `List`
- `Non-null`

## Descriptions

A **description** is like a *doc-string* or a *viewable/surface-able comment*.

**Syntax:**
- *Single:*  `"This is a description"`
- *Multi-line:* `"""This is also a description"""`

Examples:
```graphql
type Query {
    "The ID comes from Auth0"
    user {
        id: ID!
    }

    """
    The different permissions are:
    - admin: everything
    - pro-user: access to forums
    - basic-user: access to just code
    """
    permissions {
        ...
    }
}
```

## Scalars
*Note:* The primitive/scalar values are **capitalized**.

- `Int`
    - 32-bit
- `Float`
    - 64-bit, double-precision
- `String`
    - UTF-8
- `Boolean`
- `ID`
    - Unique, serializable as a string

### Custom Scalars

You can make your own scalars/datatypes!

**Syntax:** `scalar <Name>`
That's it.
It just needs to be seriailizable.

The details are determined on the server/implementation side.

## Enums

Enums are serialized as *strings* (so not like TypeScript where they're `number` unless explicitly made as strings).

## Field arguments

You already know about arguments, but a new thing is **default values**:
`instrument(type: String = "Guitar")`

## Directives

Directives can be declared in schemas.

**Syntax:** `directive @<name>(<param>: <param-type>) [repeatable?] [on <location*>]`

\**location* here is a weird name. It kind of means on what tag/keyword you can use the directive on. It can be on *both* executable and schema documents.

Examples of locations include:
- Executable:
    - `QUERY`
    - `MUTATION`
    - `SUBSCRIPTION`
    - `FIELD`
    - `FRAGMENT_SPREAD`
    - more
- Schema:
    - `SCHEMA`
    - `SCALAR`
    - `OBJECT`
    - `INTERFACE`
    - `FIELD_DEFINITION`
    - more

**Note:**  Directives can be applied to *multiple* locations too.
The book uses the example of applying a directive (`@deprecated`) on both a `FIELD_DECLARATION` and `ENUM_VALUE` to be able to put `@deprecated` on either an enum value or next to a key's/field's value (e.g. `password: String @deprecated()`)

## Extending

The `extend` keyword can be used to add onto any type.
I thought it was just for federation!

## Introspection

This one always seemed mysterious to me.
You can query a server for information about its own schema.

There are three entry fields:
- `__schema: __Schema!`
- `__type(name: String!): __Type`
- `__typename: String`
    - this is only applicable to Objects, Interfaces, and Unions

If curious for more, check out the [docs](https://spec.graphql.org/draft/#sec-Schema-Introspection)
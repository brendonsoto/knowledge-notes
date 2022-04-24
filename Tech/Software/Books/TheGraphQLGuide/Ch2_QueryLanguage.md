---
aliases: 
created: 2022-02-28, 7:14:10 pm (Monday, February 28th)
updated: 2022-02-28, 8:07:26 pm (Monday, February 28th)
---

## Terminology

A **document** refers to a *GraphQL file or string* in the same way you talk about a JSON file or string.

A **selection set** refers to the fields within a query.
## Types of documents


There are two types of GraphQL documents:
- *executable*
    - an operation or [[Tech/Software/Books/TheGraphQLGuide/Ch2_QueryLanguage#Fragment|fragment]]
- *schema*

## Field aliases

**Syntax:** `<alias-name>: field(any-arguments)`

The idea is that the `<alias-name>` becomes the key for the `field`.
The example the book gives is through querying for two pieces of data w/ the same key, but with different names.

## Fragment

A **fragment** *groups similar fields* together for re-use w/o duplication.
There are two types: *named* and *inline*

**Syntax (named):** `fragment <name> on <type> { ... }`

Example:
```graphql
fragment userFields on User {
    id
    name
    avatarUrl
    email
}

query {
    repository(id: 1) {
        contributors {
            ...userFields
        }
        starGazers {
            ...userFields
        }
    }
}
```

**Note:** Fragments can be for fields *specific to an interface* as well

**Syntax (inline):**
```graphql
query {
    repository(id: 1) {
        contributors {
            ... on User {
                email
            }
            ... on Bot {
                name
            }
        }
    }
}
```

## Directives

A **directive** has syntax similar to a *decorator*: `@<directive>`

There are three native directives:
- `@skip`
    - Full syntax: `@skip(if: Boolean!)`
    - essentially omits the field if the condition is true
- `@include`
    - Full syntax: `@include(if: Boolean!)`
    - opposite of `@skip`
- `@deprecated`
    - Full syntax: `@deprecated(reason: String)`
    - used to communicate a field is not to be used and why

For its declaration see [[Tech/Software/Books/TheGraphQLGuide/Ch3_TypeSystem#Directives|Directives]]


## Mutations

If *multiple root fields* are listed in a mutation, they are operated on sequentially, not in parallel.
---
aliases: 
created: 2022-03-01, 8:36:23 am (Tuesday, March 1st)
updated: 2022-03-01, 8:59:08 am (Tuesday, March 1st)
---
**Execution** describes the process of providing a response to a GraphQL request.
Third party libs handle part of this, but the [spec](https://spec.graphql.org/draft/#sec-Execution) has more info too.

Execution usually has three parts:
- resolvers
- response format
- errors

## Resolvers

Resolvers are called with four arguments:
- `object`
    - The object returned from the parent resolver
    - Not used for root fields
- `arguments`
    - it's what you think it is
- `context`
    - an object containing common things to be accessed by *all* resolvers (e.g. user info, db connections, etc)
- `info`
    - metadata about the current query and schema

**Note:** You don't need to provide resolvers for getting basic values from properties like `object.fieldname` (e.g. `user.id`)

**Syntax**
```javascript
const resolvers = {
    Query: {
        book(object, arguments, context, info) {
            return context.dataSources.books.find(arguments.id)
        }
    },
    Book: {
        id(object, arguments, context, info) {
            return object.id
        },
        author(object, arguments, context, info) {
            const { firstName, lastName } = object.author
            return `${firstName} ${lastName}`
        }
    }
}
```

Object resolvers, like `Book.id` and `Book.author`, are called *in parallel*
Root fields are resolved *sequentially* though.
Additionally, any subfields on a root field are first resolved before going to the next root field.

## Response format

**Syntax:**
```json
{
    "data": { ... },
    "errors": [
        { "message": "", }
    ],
    "extensions": { ... }
}
```

The `data` value contains any info returned from the server.

`errors` is what you think it is.
**Note:** There are more keys on `errors` than just `message`: https://spec.graphql.org/draft/#sec-Errors.Error-result-format
The `path` key refers to the path in the *returned data* where the problem occurs.
Any numbers are indices and are zero-based.

`extensions` is to hold anything extra the server wants to provide that's outside of the GraphQL spec.
**Note:** Two common additions to `extensions` are `code`, like an error code, and `timestamp`.
---
aliases: 
created: 2022-03-07, 11:07:18 am (Monday, March 7th)
updated: 2022-03-07, 11:14:53 am (Monday, March 7th)
---
It's very similar to writing a resolver
```javascript
const resolvers = {
  // ...the usual resolvers
  User() {
    __resolveReference(
        object, // this is data from another service
        
    )
  }
}
```

The `__resolveReference` function has three arguments:
- `object`
    - This is the reference data from another service.
        - For example, imagine a `User` object where the *entity* is owned by the *UsersService* and is being referenced in a *ShopsService* (let's say a `User` can have many `Shops`). Let's also say the ShopService's schema document refers to `User` objects only through the `id` property. A query from the ShopsService that involves `User`, let's say where `User.id === 1`, would go through the resolver in the UsersService and look for `__resolveReference` in the `User` resolver. The `object` field would be equivalent to `{ id: 1 }`
    - `context`
        - same as other resolvers!
    - `info`
        - I believe it's the same as other resolvers too!

## Resources

https://www.apollographql.com/docs/federation/api/apollo-subgraph/#__resolvereference

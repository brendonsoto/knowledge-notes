---
aliases: 
created: 2022-01-18, 4:31:42 pm (Tuesday, January 18th)
updated: 2022-01-19, 2:09:01 pm (Wednesday, January 19th)
---
## Library Agnostic

There's also `@Param(key?: string)` that returns either `req.params` or `req.params[key]` depending on whether `key` is passed to the decorator or not.

There's also `@Query(key?: string)` which operates the same.
## With Express
Use the `@Req` decorator and the `Request` type from express:
```javascript
@Get()
findAll(@Req)
```


## Sources
- https://docs.nestjs.com/controllers#route-parameters
- https://docs.nestjs.com/controllers#library-specific-approach
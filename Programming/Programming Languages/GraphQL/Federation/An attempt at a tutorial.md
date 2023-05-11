---
aliases: 
created: 2022-03-07, 10:55:23 am (Monday, March 7th)
updated: 2022-03-07, 10:57:05 am (Monday, March 7th)
---
I need to make one for myself to understand this.

I have two services:
- `tea`
- `coffee`

Both have the structure:
```graphql
type Coffee @key(fields: "id") {
    id: ID
    name: String
    type: String
}
```

They both run

Now, how to tie these together via federation?

---


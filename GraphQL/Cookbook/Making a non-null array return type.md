---
aliases: 
created: 2022-01-07, 1:09:28 pm (Friday, January 7th)
updated: 2022-01-07, 1:12:07 pm (Friday, January 7th)
---
#graphql #how-to

Example: `items: [Item!]!`

The `!` after the brackets communicates *an array should be returned, not null*.

The `!` after `Item` communicates the array will have *no null values, just Items*.
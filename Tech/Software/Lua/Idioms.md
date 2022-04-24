---
aliases: 
created: 2022-03-06, 8:35:22 pm (Sunday, March 6th)
updated: 2022-03-06, 9:45:35 pm (Sunday, March 6th)
---
## Assignments
Lua does not have shortcuts for *incrementing/decrementing numbers* (e.g. `x -= 1 -- This is incorrect`)

Lua does not support *chained assignment* (e.g. `a = b = c`)

Lua supports *parallel assignments* (e.g. `a, b, c = 1, 2, 3`)

## Control flow

Lua does not supporot `continue`

## Arrays / Tables

### Indexing tables

**IMPORTANT**
Unfortunately, it starts at 1.

### Iterating tables

Use `ipairs` since it will stop at the first *non-intiailized* index (where `table[index] == nil`).

## Regex

Lua does not support *regex*

## Scope

All variables are **global** unless specified otherwise via `local`.

## Type auto-conversions

Just like JavaScript, a `string` may be auto-converted into a `number` and vice-versa (e.g. `print(2 + '3') -- 5`)

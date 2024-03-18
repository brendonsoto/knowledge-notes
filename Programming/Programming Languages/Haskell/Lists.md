---
tags: 
- haskell
- syntax
created: Friday, March 15, 2024 5:52 PM
created_at: 2024-03-15T17:52:42-04:00
---
Use `[]`.

```haskell
oddNums = [1, 3, 5, 7, 9]
```

The *cons* operator (`:`) can also be used to construct lists.

```haskell
nums = 1:2:3:[] -- note the empty list at the end. that's needed
```

## Ranges

You can specify a range between two values using `..`.

```haskell
numsUpToTen = [0, 1 .. 10] -- straightforward incrementing
alphabet = ['a'..'z'] -- can work with certain other types too
oddNumsUpToTen = [2, 4 .. 10]
```

## Operations that are good to know

### Combining two lists

```haskell
fromOneToTen = [1..5] ++ [6..10]
```
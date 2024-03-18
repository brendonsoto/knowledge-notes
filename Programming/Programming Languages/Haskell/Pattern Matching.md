---
tags: 
- haskell
- syntax
created: Friday, March 15, 2024 5:51 PM
created_at: 2024-03-15T17:51:51-04:00
---
Pattern matching is like syntactic sugar for `if/else`, similar to a `switch` statement.

```haskell
areYouTellingTheTruth statement =
  case statement of
    True -> "I knew I could count on you!"
    False -> "Why you lying, little, ..."
```

You can use the wildcard character, `_`, for moments where you don't care about the value.

```haskell
typeOfFoodBySlicesOfBread slices =
  case slices of
    1 -> "That's a wrap!"
    2 -> "A classic sandwich"
    _ -> "Now you're just showing off!"
```
 
 It also allows us to write functions that look like overloaded functions (when you write the same function multiple times but with different arguments) but instead of changing the number of arguments we're specifying specific arguments. The `head` and `tail` functions are good examples of this.

```haskell
head [1..10] -- returns 1

myHead [] = [] -- pattern matching when given an empty list
myHead (x:xs) = x -- pattern matching when there's at least 1 elem
```
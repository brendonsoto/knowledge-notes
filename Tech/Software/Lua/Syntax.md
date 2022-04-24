---
aliases: 
created: 2022-03-06, 8:32:09 pm (Sunday, March 6th)
updated: 2022-03-06, 9:49:47 pm (Sunday, March 6th)
---
## Arrays
See [[Tech/Software/Lua/Syntax#Tables arrays]].

## Comments
```lua
-- Single line comment

-- [[
    This is a 
    multi-line
    comment.
-- ]]
```

## Scope

### local

The `local` keyword is used to scope a variable.
In Lua **all variables are global** *unless* if they are after the `local` keyword.

## Math

### Division

Division in lua can be carried out using either `/` for *floating-point* division or `//` for *flooring integer division*

## Comparing operators

- `==` - equal
- `-=` - not equal
- `>`
- `<`
- `>=`
- `<=`

## Logic

- `true`
- `false`
    - can also be represented by `nil`

**NOTE:**  Anything not `false` or `nil` is considered `true`.

### Operators
- `and`
- `or`
- `not`

## Control flow

### Conditional statements

- `if`
- `elseif`
- `else`
- `end`

Example:
```lua
if (x > y) then
    print("greater")
elseif (x < y)
    print("lesser")
else
    print("equal")
end
```

### Loops
#### while

```lua
local x = 0

while x < 5 do
    print(x)
end
```

#### repeat

Kind of like a `do while` statement:

```lua
local x = 0

repeat
    print(x)
    x = x + 1
until x > 5
```

#### for

```lua
-- [[
Syntax:
for <var> = <init-val>, <end-val>, <step> do
    <body>
end

NOTE: <step> may be omitted. If so, `1` will be the value used.
-- ]]

for x = 0, 5, 1 do
    print(x)
end
```

#### break

Similar to `break` you know in other languages (e.g. JavaScript)

```lua
local x = 0

while true do
    print(x)
    if x == 5 then
        break
    end
end
```

## Tables (arrays)

A *table* is an *associative array*.
This means they are *key/value pairs*.

### Instantiating

`local T = { 1, 2, 3 }`

### Appending

At a *specific index*: `T[4] = 4`

At the *next/last consecutive index* `table.insert(T, 5) -- T[5] == 5`

### Iterating

```lua
for index, value in ipairs(T) do
    print(index, value)
end
```

### Delete a key/value pair

`T[5] = nil -- T is now { 1, 2, 3, 4 }`

Alternatively:
`table.remove(T, 5)`
---
aliases: 
created: 2022-03-06, 8:39:46 pm (Sunday, March 6th)
updated: 2022-03-06, 8:44:14 pm (Sunday, March 6th)
---
- `nil`
    - absence of a value
    - equivalent to `null` in JavaScript
    - you can assign a variable to `nil` to **delete** it
- `boolean`
- `number`
    - Up until Lua 5.2, numbers were represented w/ double-precision floating-point
    - Lua 5.3 and onwards uses 64-bit for *integer* and double precision for *floating-point*
    - A `number` **will be converted** if used in an operation with a `string`
- `string`
    - A `string` **will be converted** if used in an operation with a `number`
- `userdata`
- `function`
- `thread`
- `table`
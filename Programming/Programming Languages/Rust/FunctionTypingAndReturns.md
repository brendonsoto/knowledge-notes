If a function returns a value, that value's type *must* be included in the function type signature.
Example: `fn addTwoNums(x: i32, y: i32) -> i32`.

One weird thing is that Rust features **implicit returns** similar to Ruby.
Using the above function again: `fn addTwoNums(x: i32, y: i32) -> i32 { x + y }`
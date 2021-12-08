#book  #rust  #the-rust-programming-language 

# Common Programming Concepts
*Started: 2021-Dec-6*
*Ended:*

> “This chapter covers concepts that appear in almost every programming language and how they work in Rust.”

- Rust favors immutability
- prefix a variable name w/ `mut` to make it mutable
  - i.e. `let mut x = 5; x = 6`

## Constants
- syntax: `const x = ...`
- Constants can only be set to *expressions*, not function results
- convention is `const ALL_CAPS_WITH_UNDERSCORES`

## Shadowing
- when you make a variable with the `let` keyword and a variable name that *already exists*
- refers to re-defining an existing variable by re-declaring it (i.e. using `let` multiple times)
- the variable can be re-used w/in the new declaration
- can **change type** of variable

```rust
let x = 5;
let x = x * 2;
println!("X is {}", x)
```

How is this helpful?
- this is a way of changing a variable *in the moment* and *then* marking it as immutable
- variable names that are simple and contextually meaningful can be reused
  - the book uses the idea of `spaces` as a string to communicate placeholder and then resetting it to a number

## Data Types
- **type annotations** how-to: `let x: u32 = 42`
  - the above says "x is an unsigned 32 bit integer whose value is 42"
  
### Scalar Types
- Refers to single value

#### integers
- there are multiple integer types signed (`i32`) & unsigned (`u32`)
- default = `i32`
- be aware of **integer overflow**
  - Rust's default behavior is to wrap the number (i.e. 255 as max for 0..2^8, 256 -> 0, 257 -> 1, etc.)

#### floats
- default= `f64`
  - on modern CPUs it's about the same speed as `f32` and has more precision

#### Booleans
- type annotation: `bool`

#### characters 
- char literal: `'c'`
- Unicode Scalar Value (can support emojis!)

### Compound Types
#### Tuple
- fixed length
- comma separated in parenthesis
  - example: `let tup: (i32, f32) = (1, 2.2)`
- pattern matching can be used to extract values
  - using the previous example: `let (x, y) = tup;`
  - the term *destructuring* is used here too
- another way to destructur is by using `variable.index`
  - example: `let y = tup.1; // 2.2`
  
  #### Array
  # YOU LEFT OFF HERE

## Quotes
> “There are multiple trade-offs to consider in addition to the prevention of bugs. For example, in cases where you’re using large data structures, mutating an instance in place may be faster than copying and returning newly allocated instances. With smaller data structures, creating new instances and writing in a more functional programming style may be easier to think through, so lower performance might be a worthwhile penalty for gaining that clarity.”

## Questions
### Can you ignore values when pattern matching?
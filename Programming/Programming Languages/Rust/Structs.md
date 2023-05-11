## C-style struct
```rust
struct RGBAColor {
    red: i8,
    green: i8,
    blue: i8,
    alpha: f32,
}

let myCOlor = RGBAColor {
    red: 255,
    green: 211,
    blue: 156,
    alpha: 0.1
}; // Note teh semicolon here but not in the declaration!
```

## Tuple style struct
```rust
struct Coordinates(f64, f64)

let myLocation = Coordinates(0.1234, 0.5678);
```

## Unit-like
These don't have fields.
I don't know yet the value of these types of structs.
```rust
struct ThisIsIt;

let whatIsIt = ThisIsIt;
```
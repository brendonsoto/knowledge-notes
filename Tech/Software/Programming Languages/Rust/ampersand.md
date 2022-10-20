tl;dr - [referencing](https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html); you're setting a pointer to the value

Look at this code:
```rust
struct Rect { width: u32, height: u32 }

fn main() {
    let rect1 = Rect { width: 10, height: 20 };
    println!("The area of the rectangle is {}", area(&rect1))
}

fn area(rect: &Rect) -> u32 {
    rect.width * rect.height
}
```

This code works if you removed the ampersands from `&rect1` and `&Rect`. So why the ampersand?

This has to do with **ownership**!

The ampersand creates a **reference** to the data. This way the  other function isn't owning the data and as a result that data is freed after the function call.
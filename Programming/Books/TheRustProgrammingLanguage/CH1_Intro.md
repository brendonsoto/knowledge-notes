#book  #rust  #the-rust-programming-language

# The Rust Programming Language: Intro
## Foreword
The authors of this section mentioned *empowerment* as a quality of Rust
Rust lowers the barrier of entry for programs related to memory management and concurrency
The authors also mention that while Rust handles a lot of "system-level" programming really well, it's also suitable for other domains
Examples of CLI apps and web servers, both example projects of the book, were given

## Preface
Book assumes using _Rust 1.31.0_ or later w/ `edition="2018` in /Cargo.toml/ files
There have been several big updates to the book to reflect the changes in the 2018 edition

I have Rust 1.56.1 at the time

## Acknowledgments
  Nice

## Introduction
  The crab is cute!

  Rust tries to find the balance between the ergonomics of high-level langs and the control of low-level langs

 ### Who is Rust for
Rust's compiler can be used to help prevent bugs allowing developers to focus on logic/big picture

**Tools in the Rust world:**
- Cargo
-- **dependency manager**
-- also a **build tool**
- Rustfmt
-- formatting tool
- Rust Language Server
-- LSP!!!!! <3

Rust is also mentioned as suitable for students who want to learn about system concepts like operating systems development

> Through efforts such as this book, the Rust teams want to make systems concepts more accessible to more people, especially those new to programming. (p34)

Interesting...makes me wonder if systems development is a field needing more people

Rust is apparently used in bioinformatics?
Sounds cool

> Rust is for people who crave speed and stability in a language. (p34)

Speed here defined as both the time to create programs in Rust as well as how fast those programs can run
Rust = Safety + Productivity && speed + ergonomics
(things that are usually considered one or the other)

 ### Who this book is for
Doesn't talk about how to think about programming

 ### How to use this book
- book assumes reading it front to back
- chapters build upon each other
- concept chapters & project chapters
-- project chapters: 2, 12, 20

Chapter overview
- 1: Installing Rust, Hello World, Cargo 101
- 2: Hands-on high-level intro to Rust
- 3: How Rust is similar to other languages
- 4: Rust's ownership system
- 5: Structs and methods
- 6: Enums, `match` expressions, `if/let` control flow, creating custom types
- 7: Rust's module system, privacy rules for organizing code, public API
- 8: Standard library data structures (strings, vectors, hash maps)
- 9: Error handling
- 10: Generics, traits, lifetimes
- 11: Testing
- 12: Building a watered-down `grep`
- 13: Closures and iterators (Functional programming stuff)
- 14: More Cargo (best practices for sharing libraries for others)
- 15: Smart pointers
- 16: Concurrent programming
- 17: Rust idioms compared to OOP principles
- 18: Reference on patterns and pattern matching
- 19: Multiple advanced topic primers (unsafe Rust, macros, more on traits, types, functions, and closures)
- 20: Low-level multithreaded web server

Appendices:
- A: Rust's keywords
- B: Rust's symbols and operators
- C: Derivable traits from standard library
- D: Helpful development tools
- E: Rust editions explanation

> ...if you’re a particularly meticulous learner who prefers to learn every detail before moving on to the next, you might want to skip Chapter 2 and go straight to Chapter 3, returning to Chapter 2 when you’d like to work on a project applying the details you’ve learned. (p36)
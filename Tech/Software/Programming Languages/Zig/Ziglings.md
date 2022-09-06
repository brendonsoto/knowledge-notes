[https://github.com/ratfactor/ziglings]

Similar to Rustlings / Ruby Koans -- the idea of teaching a language with a bunch of little broken programs.

Going to use the "chapter" number as the subheadings and list what I've learned under.

## 1
- Functions in zig are private by default
- Use the `public` keyword to make a function public
- The `main` function is expected to be public

## 2
- import libraries using `const <lib-name> = @import("<lib-name>");`
    - `@import` is a function whose return value somehow is the entire library.
        I guess it's like a name-spaced thing.
- zig uses *lazy evaluation*
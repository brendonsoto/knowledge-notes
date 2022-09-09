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

---

I stopped here because I simply forgot.
I'm only on ex 7 now, but think noting every small thing I learned here wouldn't actually be useful for me as a reference.
It may help with retaining the information, like moving it into long-term-ish memory, but that's not the point of this repo.

Instead I'm using git tags to set up arbitrary checkpoints to jot down things I learned.
Check my fork of ziglings for those tags.
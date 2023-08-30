---
tags: haskell
created: Tuesday, August 29, 2023 11:06 PM
created_at: 2023-08-29T23:06:37-04:00
---
## On getting started and the relationship between GHC and Stack
2023-Aug-29

Getting into Haskell as a beginner is simultaneously simple and not simple.

To start off, it's weird going from haskell's main site to what looks like a different site but is within the same domain to learn about the language. The installation process and TUI is nice and straight-forward.

What confuses me is the relationship between Stack and GHC. The [getting started page](https://www.haskell.org/get-started/)makes me think GHC is separate from Stack but the [Stack website](https://docs.haskellstack.org/en/stable/) mentions Stack installs GHC automatically. On top of that, Stack is listed as an alternative build tool to Cabal. 

## On tooling
2023-Aug-29

At the time of writing I'm using Neovim with [mason](https://github.com/williamboman/mason.nvim) for managing language-dependent tooling (LSPs, DAPs, linters, and formatters). Haskell has its own [language server](https://github.com/haskell/haskell-language-server). (Side - I'm stoked it's working because a few years ago when I first was learning Haskell the dang language server was a total resource suck!). It can use different formatters but the default is [ormolu](https://github.com/tweag/ormolu). It's not clear that ormolu is installed too when installing the language server. 

Additionally, ormolu seems to error out on what seems like a basic case:
```haskell
inFirstHalf xs x = elem x firstHalf
where firstHalf = take (div (length xs) 2) xs 
```
Having `where` at the beginning of a line apparently causes ormolu to error.


## On lazy evaluation
2023-Aug-29

This is from reading Lesson/Chapter 6: Lists from [Get Programming With Haskell](https://www.manning.com/books/get-programming-with-haskell):

> Lazy evaluation has advantages and disadvantages.... The disadvantages of lazy evaluation are less obvious. The biggest one is that it's much harder to reason about the code's performance.... An even bigger problem is that you can easily build up large collections of unevaluated functions that would be much cheaper to store as values.

The idea of obscuring reasoning about a program's performance makes me a bit uneasy, but I guess there are similar things in other programming languages.


## On installing (and uninstalling) stuff with Stack
2023-Aug-29

For context, I was trying out the ormolu formatter prior to using the language server. I installed it via `stack install ormolu`. That was fine. Uninstalling it to see if I actually didn't need it after installing the language server was confusing.

To _uninstall_ a program installed with Stack you need to find where the program was installed and manually delete it.

It does not make sense to me to have `stack install <program>` but no `stack uninstall <program>`. That is not user-friendly. Here's [one issues thread](https://github.com/commercialhaskell/stack/issues/361) on the matter where the owners said:
> I'm quite tempted to close as wontfix. I haven't seen the use case clearly demonstrated that stack uninstall would be useful. I know others ask for this all the time though, which is why I'll leave this open a bit longer.

I get that Stack's a build tool and not necessarily a package manager, but it's also used as a package manager. I kind of understand the idea of building the project and only moving the binary over to a certain location, but I still feel like there should be a matching "undo" command.
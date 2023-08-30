---
tags: haskell
created: Tuesday, August 29, 2023 11:06 PM
created_at: 2023-08-29T23:06:37-04:00
---
## On getting started and the relationship between GHC and Stack
Getting into Haskell as a beginner is simultaneously simple and not simple.

To start off, it's weird going from haskell's main site to what looks like a different site but is within the same domain to learn about the language. The installation process and TUI is nice and straight-forward.

What confuses me is the relationship between Stack and GHC. The [getting started page](https://www.haskell.org/get-started/)makes me think GHC is separate from Stack but the [Stack website](https://docs.haskellstack.org/en/stable/) mentions Stack installs GHC automatically. On top of that, Stack is listed as an alternative build tool to Cabal. 

## On tooling
At the time of writing I'm using Neovim with [mason](https://github.com/williamboman/mason.nvim) for managing language-dependent tooling (LSPs, DAPs, linters, and formatters). Haskell has its own [language server](https://github.com/haskell/haskell-language-server). (Side - I'm stoked it's working because a few years ago when I first was learning Haskell the dang language server was a total resource suck!). It can use different formatters but the default is [ormolu](https://github.com/tweag/ormolu). It's not clear that ormolu is installed too when installing the language server. 

Additionally, ormolu seems to error out on what seems like a basic case:
```haskell
inFirstHalf xs x = elem x firstHalf
where firstHalf = take (div (length xs) 2) xs 
```
Having `where` at the beginning of a line apparently causes ormolu to error.
---
tags: haskell programming
created: Tuesday, June 27, 2023 10:18 PM
created_at: 2023-06-27T22:18:05-04:00
---
To launch a REPL: `ghci`
To load a module/file into the REPL: `ghci my-file.hs` or `ghci` and once in `:l my-file.hs`

## Configuration

You can configure how ghci should behave through creating a `.ghci` file (I have mine located at `~`). For example, at the time of writing I have the configuration setup to use neovim as an editor:
```
:set editor nvim
```
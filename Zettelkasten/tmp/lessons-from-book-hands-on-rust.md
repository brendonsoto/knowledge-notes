# Lessons from the book Hands on Rust

## Part I: Build your First Game with Rust
### Understanding the Game Loop
1. Setup Graphics, Windows, App
2. Poll for input
3. Call the `tick` function
    - `tick` is where computing any changes to the state happens
4. Update the screen
5. Check if the user is telling the game to quit
    - if so, game/app ends
    - otherwise, return to step 2.

### Creating Different Game Modes
Think of *modes* kind of like modes in Vim.
A mode allows certain kinds of actions in it.
The book describes the Flappy Dragon game as having three modes:
- Menu
- Playing
- End

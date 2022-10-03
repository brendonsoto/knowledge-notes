## Pre 1.0
This confused me a bit so I'm spelling it out for myself:
*NOTE: These were written when I was using v0.10-dev*

- Download one of the *binary* formats from [https://ziglang.org/download/]
- Check the checksum if you're feeling paranoid . See [sha256 and checksums](Tech/Software/Operating%20Systems/Unix/Commands%20Cheatsheet.md#sha256%20and%20checksums)
- Once installed, add the path to the *whole directory* to your path
    - This is because some of the directories within the zig dir are used for other commands (e.g. `zig init-exe` uses stuff from `$ZIG_DIR/lib/init-exe/`)
- Run `zig version` to confirm all is well
    - Can also run `zig init-exe` or `zig env` to make sure all is well
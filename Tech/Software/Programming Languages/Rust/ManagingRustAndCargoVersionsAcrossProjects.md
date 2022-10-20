This is *really* neat.
All you need is `cargo`.
No joke.

At the time of writing (2022-Sep-28), I'm using Rust 1.64.
I was going through the Rust book again from the start and thought, "What if I opened up the source code behind a real app I use that's built with Rust to look for parallels?"
I opened up Zellij's source and checked it's `Cargo.toml` file to see it was built using an older version.
I just ran `cargo build` and started seeing a different version of Rust alongside its toolchain *and* the dependencies for the project installing.
This is wonderful.

If curious, building Zellij took ~5 minutes (4m46s).
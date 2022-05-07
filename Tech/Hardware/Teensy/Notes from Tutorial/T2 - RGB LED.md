---
aliases: 
created: 2022-04-30, 7:25:23 am (Saturday, April 30th)
updated: 2022-04-30, 8:29:19 pm (Saturday, April 30th)
---
This was interesting!
I spent a bit of time wondering why I couldn't get the LED to light up until I checked Adafruit for more on the type of LED I got.
Turns out, it's connectivity is the opposite of what the tutorial has!
Power goes into the common pin instead of ground.

While that made following along a little more confusing, the big takeaways I got from working with the Teensy were:

- *Semi-colons are important here!*
- `digitalWrite(<pin>, <HIGH | LOW>)`
- `analogWrite(<pin>, <number-value>)`
- `const` is used to declare constants
- `int` is used for numbers
- variables are mutable
- `delay(<time-in-ms>)`
- `pinMode(<pin-number>, <OUTPUT | ...?>)`
- [[Tech/Hardware/Teensy/Life Cycle|Life-cycle functions]]

## Questions
### Where can I find the docs for what functions are available?
[[Tech/Hardware/Teensy/Available Functions|Added docs here]]
Found it in Arduino IDE via `Help > Reference`

### How much voltage do the pins output?
[[Tech/Hardware/Teensy/Output Values|Output Values]]

## Other thoughts
Part of me wants to try the CLI route again, but that's because I want to use Vim for navigating instead of the mouse.
Additionally, I wonder if there's a sort of Arduino/Teensy linter and tooling for the CLI.
[This](https://github.com/williamboman/nvim-lsp-installer/blob/main/lua/nvim-lsp-installer/servers/arduino_language_server/README.md) looks promising...

## Related
[[Tech/Hardware/Teensy/Notes from Tutorial/T2 - RGB LED Variation]]
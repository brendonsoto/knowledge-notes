---
aliases: 
created: 2022-05-12, 7:34:35 pm (Thursday, May 12th)
updated: 2022-05-12, 7:47:28 pm (Thursday, May 12th)
---
See [the docs](https://www.pjrc.com/teensy/td_libs_Encoder.html) for a helpful overview.
For connecting the encoder to the Teensy, look [[Tech/Hardware/Teensy/Working with components/Encoders|here]]

There are **examples** in *File > Examples > Encoder*.

The **interface** is as follows:
- `Encoder <varName>(pin1, pin2)`
- `myEnc.read()`
- `myEnc.write(newPosition)`

The pins for the encoder can be any **digital** pins.
The **value** returned from the encoder functions are **number**s.

## Related
[[Tech/Hardware/Teensy/Working with components/Encoders]]
---
aliases: 
created: 2022-05-06, 9:10:26 pm (Friday, May 6th)
updated: 2022-05-06, 9:23:34 pm (Friday, May 6th)
---
This project I did only a portion of it.
I really have no interest nor motivation for exploring the thermoresistor side of things.
Additionally, the color LED related examples have been odd to follow along because the only way I have to manipulate the LED right now is through one entry point.
While usually I'd think this is fine, I'm having trouble understanding the datasheet so I don't really know what I'm doing.
All I've been doing is slapping at least one resistor at the common pin (I forgot if anode or cathode) and experimenting with adding others both in series and in parallel.
I remember resistors in series produces a resistance that is the sum of the two/N resistors and that resistors in parallel essentially is the quotient of those resistors.
I relearned how to read the values of resistors.
However, I did forget how to derive current given just voltage and resistance.
I feel like it's `V = IR`, but I don't trust my memory.

Anywho, I don't have a multimeter yet to take any measurements so I can only theorize about what the values are.

I did do the analog read portion of the tutorial and found that to be cool.
I was *confused* that the Teensy reported the analog read input to be at it's max (1024) when the trim pot was about 75% rotated.
Not sure what that's about...

I think at this point, I can roughly figure out the next parts.
I want my next goals to be:
- figure out how to use vim/CLI instead of teensyduino

- learn how to use an encoder
- learn how to manipulate LEDs better
- learn how to read a datasheet better
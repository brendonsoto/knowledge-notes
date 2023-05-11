---
aliases: 
created: 2022-05-06, 9:23:44 pm (Friday, May 6th)
updated: 2022-05-12, 8:35:02 pm (Thursday, May 12th)
---
From [[Electronics/Teensy/Notes from Tutorial/T3 - Serial Monitor and Input]]:

- What is baud rate?
- Why is a pull up resistor necessary?


From [[Electronics/Teensy/Notes from Tutorial/T4 - Analog Input]]:

- Figure out how to use vim/CLI instead of teensyduino
- Learn how to use an encoder
- Learn how to manipulate LEDs better
- Learn how to read a datasheet better

From playing with [[Electronics/Teensy/Working with components/Encoders]]:

- how to smooth the values read?
    - people online say this has to do with the quality of the encoder
    - Look into the [[Electronics/Sensors/Rotary Encoder#Resolution|Resolution]] part
        - I think I could "smoothen" the values out by doing some math trickery, modulus or having some counter that counts up to 4 and then resets, using the reset as the time to increment the value by 1
- what is an "interrupt?"
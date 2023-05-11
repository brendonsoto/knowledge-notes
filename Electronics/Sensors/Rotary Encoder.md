---
aliases: 
created: 2022-05-12, 7:27:32 pm (Thursday, May 12th)
updated: 2022-05-12, 8:32:38 pm (Thursday, May 12th)
---
There are different types of encoders.
The ones you have/started out with are **quadrature**.

## Quadrature
These have 2 square wave outputs that are 90 degrees out of phase with each other.
As you turn the knob, the 2 signals can be used to detect which direction you're going in.

The **connections** for the encoder are as follows.
There should be a side with *three pins*.
The **outer** pins should connect with to a **digital input** while the **inner** pin should be connected to **ground**.

## Push button functionality
Sometimes the encoder can have a **push** button functionality to it too.
If there are *two pins* on the other side of the encoder, those are for the push button functionality.
It works like any other momentary switch.

## Detents

^af6cfb

Detents is a term used to describe the clicky-ness an encoder may exhibit.
Detents is expressed in a number.
That number describes the number of "clicks" that can be felt in one full rotation (360 degrees)

Kudos this [stackExchange post](https://electronics.stackexchange.com/questions/64706/rotary-encoder-detents)

## Resolution
This is related to [[Electronics/Sensors/Rotary Encoder#Detents|detents]]; you may observe when using an encoder that one "click" outputs a value greater than 1.
For instance, I started with [this encoder](https://www.adafruit.com/product/377) and every "click" would increment the value in the Serial monitor by 4.
I couldn't find anything specific on the [datasheet](https://cdn-shop.adafruit.com/datasheets/pec11.pdf) to explain this.
However, I did find [this helpful article](https://www.student-circuit.com/blog/understanding-encoder-resolution-and-how-to-interpret-the-datasheet/) that hinted to me the problem may be due to the *number of bits* the encoder uses.

This reminded me of that [sparkfun page](https://www.student-circuit.com/blog/understanding-encoder-resolution-and-how-to-interpret-the-datasheet/) I found about encoders and how 2 bits can be used to determine direction.
The reasoning for why the values would be in steps of four makes sense after looking at the grid.
Follow the pattern of `0, 1, 3, 2` or `0, 2, 3, 1` (the two below the grid) against the grid's values and you'll end up with `-4` or `4` (if you end up at `+/-3`, consider going from the last value back to the first. Using the first pattern as an example  `0, 1, 3, 2, 0`).

## Pros
- You have an "infinite" range of values to swing around.
- Some encoders have a clicky-ness to them so you can *feel* when you're switching values

## Cons
- The clicky-ness to some encoders may make them *feel* awkward
- The clicky-ness doesn't communicate a linear relationship as you rotate.
    - For instance, [this encoder](https://www.adafruit.com/product/377) jumps by four with every "click"

## Sources
https://www.dynapar.com/technology/encoder_basics/quadrature_encoder/
On Quadrature

https://cdn.sparkfun.com/datasheets/Robotics/How%20to%20use%20a%20quadrature%20encoder.pdf
An interesting grid demonstrating the binary logic for determining direction
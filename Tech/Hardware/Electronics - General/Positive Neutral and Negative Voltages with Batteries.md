---
aliases: 
created: 2022-06-07, 10:03:33 pm (Tuesday, June 7th)
updated: 2022-06-07, 10:20:25 pm (Tuesday, June 7th)
---
This is to setup a positive, neutral, and negative voltage on a breadboard with batteries.

Imagine a breadboard where the power rails on both sides are ordered, from left to right, ground (blue) then power (positive/red).
Now imagine you named your two batteries *A* and *B*.

To create your **+9V** supply, connect the *positive* terminal of battery A to the *left-hand* power rail.
For your **-9V** supply, connect the *negative* terminal of the battery B to the *right-hand* power rail.
To create a **ground** reference point, connect the *negative* terminal of battery A to the *left-hand* ground rail *and* connect the *positive* terminal of battery B to the *left-hand* ground rail too.

At this point you should have *three connections*:
- positive terminal of battery A to left-hand power rail
- negative terminal of battery B to right-hand power rail
- negative terminal of battery A to left-hand ground rail *and* positive terminal of battery B to left-hand ground rail

## Why does this work?
You have two batteries of equal voltage, 9V.
9+9=18
You need a reference point to call "ground" and you have two sources of the same voltage.
If you were to connect them in series (e.g. positive terminal of A to power rail, negative terminal to B's positive terminal, and lastly negative terminal B to ground rail) your voltage range would be from 0V-18V.
By introducing an access point to the electricity between the negative terminal of battery A to the positive terminal of battery B, you're essentially splitting the voltage in half.

## Images
A version I got from Moritz Klein's [breadboard video](https://www.youtube.com/watch?v=XpMZoR3fgd0):
![[pos-neutral-neg-battery-setup-2.jpeg]]

My original kind-of-confusing version.
![[pos-neutral-neg-battery-setup-1.jpeg]]

A close up of the same version
![[pos-neutral-neg-battery-setup-1--close.jpeg]]
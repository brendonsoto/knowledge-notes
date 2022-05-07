---
aliases: 
created: 2022-04-30, 8:38:02 pm (Saturday, April 30th)
updated: 2022-04-30, 9:04:15 pm (Saturday, April 30th)
---
I forgot about this.
I really like [Jameco's page](https://www.jameco.com/Jameco/workshop/CircuitNotes/circuit-notes-resistors.html) on it.
For convenience, this page will be a copy of that info.

## Through-hole resistors
You'll see either resistors with either **4 or 5 colored bands**.

The total value is represented in three parts:
- a **base value**
- a **multiplier**
    - is 10^n
- a **tolerance**
    - a percentage that the value can vary by

The representation of these three parts by the 4 or 5 colors is as followed.
Note, we're going backwards for ease of expression.

The *last* band's color represents the resistor's tolerance.
The *second to last* band's color represents a **multiplier**.
It's an exponent where the base is 10 and the exponent/power is that *multiplier*.
The *first two or three* band's colors represent the resistor's **base value**.

Now for what the colors mean.

## Base value

^c2220a

Color | Value
-------|-----
Black | 0
Brown | 1
Red | 2
Orange | 3
Yellow | 4
Green | 5
Blue | 6
Violet | 7
Grey | 8
White | 9

## Multiplier
Sames as [[Tech/Hardware/Electronics - General/How to read resistor values#^c2220a|the previous section]], but with two additions:

Color | Value
-------|-----
Gold | 0.1
SIlver | 0.01

## Tolerance

Color | Value
-------|-----
Brown | 1%
Red | 2%
Gold | 5%
Silver | 10%
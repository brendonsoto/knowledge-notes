---
aliases: 
created: 2022-06-01, 8:54:06 am (Wednesday, June 1st)
updated: 2022-06-12, 8:07:31 pm (Sunday, June 12th)
---
## Checking components

### Resistors

Expected | Actual
------------ | --------
1M | 992k & 995k
100k | (99k4 x2) & 100k3 & 99k8 & (99k5 x2) & 99k6 & (100k x2)
68k | 67k6 & 67k4
47k | 4k676
33k | 32k86
14k | 1k392
1k5 | 1k494
1k | 1k007 & 996
10 | 10.0 & 10.0

### Thermistors
Should be 10k x4
Not sure how to accurately measure
I have them connected to the multimeter

They're hovering around:
- 9k64
- 9k3
- 9k5
- 9k51

## Notes from sections

### Oscillation Basics
> ...a sawtooth-wave's frequency is solely determined by the
duration of its second phase. The longer it takes for the
voltage to fall down, the lower the frequency of the
wave – and vice versa. This makes it comparably easy
to manipulate that frequency.

This is interesting to me.
I believe a capacitor has to do with the drop in voltage and thus a key component in controlling frequency.
If so, how is the frequency of a pulse wave determined?
Or is a capacitor involved in both and a resistor is used to control the speed of the capacitor discharging?

### The Oscillator Core
I really like the analogy of a capacitor being like a balloon.

So a **Schmitt Trigger Inverter** is a doo-hickey that has two inputs: one for sensing an input voltage and another that's connected to another voltage source (like power?).
Inside the component the input voltage is checked against two thresholds, a high point and a low point.
When the input voltage changes from one of those thresholds to another the *output* of the inverter changes to either a high voltage or a low voltage (sourced from the other input!).
I'm not super sure if I got this correct...

### Building the Core
When using an IC it's favorable to *connect unused inputs to ground* in order to **prevent picking up static noise**.
Static noise may make the IC act unexpectedly.

I also like the explanation for why you can't just plug in an audio socket at this point to hear the oscillation.
Picturing the addition of the socket as another path for electricity to flow that is more of a "path of least resistance" than the capacitor and thus there's no oscillation makes sense.

### Buffering, Coupling, Listening
Buffers are like Schmitt Triggers in the sense that they both have *voltage sensors*.
A **buffer** mirrors its input voltage level using the voltage sensor input.
Since the buffer uses a voltage sensor, no current flows through it and as a result they're great for representing voltage without possibly interfering with the voltage.

I got sound!

## Questions
### Why are there different types of resistors?

### Why are there different types of capacitors?

### How is it that a diode can prevent current in a direction?

### What exactly is a Schmitt Trigger Inverter?

### Why does static noise in some inputs of an IC impact other inputs/outputs/operations?
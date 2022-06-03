---
aliases: 
created: 2022-06-01, 8:54:06 am (Wednesday, June 1st)
updated: 2022-06-03, 8:59:57 am (Friday, June 3rd)
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


## Questions
### Why are there different types of resistors?

### Why are there different types of capacitors?

### How is it that a diode can prevent current in a direction?

### What exactly is a Schmitt Trigger Inverter?
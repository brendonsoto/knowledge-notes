---
aliases: 
created: 2022-06-01, 8:54:06 am (Wednesday, June 1st)
updated: 2022-06-20, 5:03:34 pm (Monday, June 20th)
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

### Changing the Frequency
A transistor can act as a kind of variable resistor.
Transistors have a quality that allows a linear change in input voltage to be reflected as an exponential change in current.
Neat!
A resistor can be connected to the base of a transistor to ensure not too much current gets to the transistor.

### Sequences, Scaling and Offsets
Voltage divider came in for scaling incoming voltages down!
The section on "shifting the center" confused me.
Oh!
I think I get it now.
I was confused on where the "constant voltage" source would be.
I see now we're using the voltage going into the transistor's base as our constant voltage.
The sequence voltage changes then are added on top of that voltage.

I did not have a sequencer by but was able to kind of mimic it using it a photo-cell resistor.
I attached the photo resistor basically where the sequencer input jack is.
I was able to vary the pitch that way.
I also did hear the change in pitch from just touching the transistors.
I also tried blowing on it to cool it down and noticed a change then too.
This is really nice to have a hands on way of exploring these concepts.

### Temperature Control
NPN and PNP transistors can be used together to tackle *temperature problems*!
The PNP transistor was introduced this time (NPN was for changing the frequency).

I needed a refresher on why the NPN transistor was needed in the first place.
It's to enable a linear change in voltage to produce an exponential change in voltage so the oscillator can span multiple octaves (using a 1V/Octave scaling).

I was a little confused why the potentiometer and sequence audio jack were removed when introducing the PNP, but upon reflection I believe that was to isolate just the transistors working together.

The PNP transistor was introduced as an **emitter follower** to be used with the NPN transistor to tackle the problem of the frequency changing when the temperature of the NPN transistor changes.
When the NPN transistor heats up it "opens up more".
The vagueness confused me.
Somehow when heat is applied, more current comes out of the emitter of the NPN transistor which also implies an increase in voltage at its base.
The PNP acts basically in the opposite way.
As head is applied, the PNP transistor "closes up" and less current is outputted.

On running the circuit, it was really interesting to hear the pitch rise and decrease as the result of touching the two transistors.

Side:
I believe what happens is the heat makes the particles move faster which means a slightly faster current and since there's an increase in current output more voltage is required to "match" so there's more of a draw at the base of the transistor.
Then again, I have no idea what I'm talking about haha.

### Tuning
I didn't know precision trimmers could rotate many times!

For the multi-voltage tuning from a sequencer section, I didn't have a sequencer like that so I resorted to making voltage dividers and am rather proud of the result!
I used [this website](https://ohmslawcalculator.com/voltage-divider-calculator) for its voltage divider calculator and basically took a trial and error approach.
I set the input and output voltages to 9V and 1V.
I then got my multimeter and sampled a few of my resistors to get an idea of the possible values I have.
Then I tried plugging it into the calculator to see if there's a possible match.
I found one that would work if I had a sort of cascading voltage divider setup.
The 2 values from the site that worked were 2.2k and 275.
I didn't have 275, but I did have 2 557Ohm resistors so I figured that would work!
I was very happy taking the measurement and seeing 0.975V on the multimeter when testing it out.
Afterwards, I tried looking up some sort of calculator or chart for Volts to Hertz using the 1V/Octave standard.
I couldn't find a chart or calculator but I did find a site saying 1V is middle C which is about 261.63Hz.
I used some algebra to figure out what Hertz I would have from using my derived voltage: x/261.63 = 0.975.
I got around 255ish so I plugged that into an online tone generator and tried tuning by ear.
I see the value in having a power supply that can supply different voltages for sure now!

I forgot to mention, I was a bit confused in determining the parallel series resistor set up.
At first I tried measuring the current in the circuit and was planning to use Ohm's law to determine what resistor to use to get the appropriate voltage.
I then realized that wouldn't really work since the voltage is fixed at 9V (ignoring that it drains over time).
I also realized I misunderstood the voltage divider math and mixed it up with the parallel resistor formula.
More lessons learned!

### Temperature trouble... again?
Skipped for now since I wouldn't have a way of really observing the change in output.

### FM Input and Fine Tuning
Skipped for now since the section mentioned it was fine to.

### Waveshaping: Sawtooth to Pulse
It's interesting seeing the comparator being used very directly/plainly here.
It kind of stinks knowing the output isn't really observable unless an oscilloscope is used.
I also don't get why the Pulse wave may potential blow out headphones right now.
How can it be loud when the sawtooth is pretty tame?

### CONTROLLING THE PULSE WIDTH WITH CV
I wish this section had a little more details to it.
I would've loved to read how the trial and error testing in picking the resistor value was done.
I would've also loved to have a little more info on how knowing the input voltage values impacts resistor choice.
Is it just calculating the current output from +/- 5V?

## Questions
### Why are there different types of resistors?

### Why are there different types of capacitors?

### How is it that a diode can prevent current in a direction?

### What exactly is a Schmitt Trigger Inverter?

### Why does static noise in some inputs of an IC impact other inputs/outputs/operations?

### Why do transistors react differently when heat is applied?

### Why does a PNP transistor have a slight increase in voltage in it's emitter?

### How is it that a PNP transistor seems to balance its output at the emitter with its input at the base?
I didn't understand the following:

> You'll probably be surprised to hear that it doesn't really matter for our purposes. As long as there is some resistor there, everything should work out just fine. Because for a given voltage at the base, the relation between the resistor and the open-ness of the transistor is always going to be approximately the same – because if the resistor value is bigger, the transistor will automatically be more closed, and if it's smaller, the transistor will be more open. That's why the emitter follower is commonly referred to as a negative current feedback circuit – its pretty much always taming itself, so that the 1:1 relation between input and output voltage is upheld in most scenarios.


# IDEAS
## Web app with interactive voltage divider/electronics math tools
Think calculating resistors in parallel/series but with sliders instead of just text boxes.
---
aliases: 
created: 2022-06-23, 12:34:12 pm (Thursday, June 23rd)
updated: 2022-06-23, 12:56:01 pm (Thursday, June 23rd)
---
I believe parasitic oscillation is used to describe unexpected oscillation caused by **positive feedback in an amplifying device**.

Sources of this positive feedback include:
- stray capacitance between input and output wiring
- mutual inductance between input and output wiring
- sufficient internal capacitance
- impedance in the power supply
    - if a common power supply is used for multiple amplification stages, the changes in current in one output stage may cause the supply voltage to vary

This seems to also be possible when using [high-gain amps](https://www.diystompboxes.com/smfforum/index.php?topic=94068.0).

## Possible remedies
The following is from the same link as the [high-gain amps](https://www.diystompboxes.com/smfforum/index.php?topic=94068.0) link:
*tl;dr - layout of your circuit plays a **big** part*

> 1. Keep outputs away from inputs, especially high impedance inputs.
> 2. Route wires so that they don't run parallel for wires from different parts of the circuit, minimizing capacitance between different parts of the circuit.
> 3. Where signals simply must go out and return from the circuit, twist the send/return lines, ideally with a ground wire too, to force the capacitance between the send and receive, and capacitance to ground to be maximum. This keeps the energy from being so widely radiated.
> 4. Where you can't do the above, use shielded wires. This is the fundamental reason coax exists. It's self shielding. It was only after coax was invented that it's transmission line properties were discovered.
> 5. Bypass the power lines and use star grounding in hard cases. Wires conducting ground and power currents also carry signals and can be a feedback path.
> 6. Don't use breadboard for tough cases. The little clips inside the breadboard have capacitances to each other. Or ground every other one, cutting the capacitive transmission a lot.
> 7. Use shield plates and so on.

## Sources
https://en.wikipedia.org/wiki/Parasitic_oscillation
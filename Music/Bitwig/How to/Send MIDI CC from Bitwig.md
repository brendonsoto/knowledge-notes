---
aliases: 
created: 2022-08-28, 8:57:00 am (Sunday, August 28th)
updated: 2022-08-28, 10:18:28 am (Sunday, August 28th)
---
## Way 1: HW Instrument > MIDI CC
To set it up:
- Add a HW Instrument device to the track
- Once your channels are setup click *Note FX*
- Click the *+* button
- Click *MIDI CC*
- Set the CC value by clicking and dragging the box with the orange text or dash
- You can rename the value by clicking the box underneath the orange text

Here's a screenshot showing a way to control the Digitone's operator A level.
*NOTE* It does look weird how the HW Instrument is targeting Ch 4 but the MIDI CC is targeting channel 1. I guess Note FX just use the Parent device's MIDI settings as an override?
*NOTE:* The digitone does not respond well to Bitwig's MIDI CC w/ LFOs :(
![[_images/Screen Shot 2022-08-28 at 9.03.30 AM.png]]

## Way 2: MIDI CC > HW Instrument
Similar to above, but you have the MIDI CC device first and then HW Instrument.
In this setup, both devices need the MIDI Channel set to the correct channel.
I think the other way makes a bit more sense, defining the HW Instrument first and then tacking on extra manipulation stuff.
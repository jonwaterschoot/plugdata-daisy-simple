---
layout: default
title: Audio in - Audio out
nav_order: 9
parent: Components Plugdata examples
---

# Name: Audio input / audio output

First things first: getting sound in or out of daisy. These are the easiest parts and require little setup.

## Function: Audio in - ADC / audio out DAC

This is pretty obvious and self explanatory. Daisy has a few pins that talk to plugdata via the blocks `adc~` and `dac~`.

ADC stands for Analog to Digital Converter = this is the input, e.g. microphone, another synth, ...
DAC stands for Digital to Analog converter = this is the output, e.g. a line out, headphones, ...

## What it looks like: most common is to use TS or TRS jacks.

### TS - TRS 
These letters stand for Tip, Ring, and Sleeve.
And they refer to the parts of the jack plug that the different conductors are connected to. A TRS cable has three conductors vs. the two on a standard guitar cable.

Looking at the plug or jack input may not show clearly how many wires it will connect. On jacks this is more obvious, you can count the parts.

Looking at your components might give you some clue, the stereo mostly has a clear extra pin vs the mono.

## Pins 16 - 19

There are 2 stereo input pins: 16 and 17;
and 2 stereo output pins, 18 and 19.

Note the pin numbers here stand for the Pins on the Daisy board - if you need an oversight of pins you can look at this spreadsheet.

You'll connect these to audio jack(s). And then you'll also connect ground to your jacks.

When using the Synthux Simple boards it will depend on which version you have whether you can connect a stereo or mono jack.

On e.g. the Simple Touch board the connections between the jacks and the Daisy board are already in place. Check the docs of your Simple board to see wether you've got this pre-configured and whether your jacks are mono or stereo.

The common multi footprint of the Simple board connectors will allow for a mono jack. You could 'hack' the extra pin by connecting an extra wire to another free pin.

- TODO insert Link to Synthux audio input / output documentation.


[Link to table overview of all pins](https://docs.google.com/spreadsheets/d/1xtg_s1tk8tm-6qNkBLFc6V1L_Mpmu-PCOvv7qEyr9mU/edit?usp=sharing) 

## Components json setup

When using these standard pins on the Daisy, 16 - 19, audio input / output pins 

If you only need mono sound you only connect 1 of each as needed.

  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources
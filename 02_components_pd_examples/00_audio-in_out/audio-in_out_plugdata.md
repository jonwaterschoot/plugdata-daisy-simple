---
layout: default
title: Audio in - Audio out
nav_order: 9
parent: Components Plugdata examples
---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Name: Audio input / audio output

First things first: getting sound in or out of daisy. These are the easiest parts and require little setup.

## Function: Audio in - ADC / audio out DAC

<img src="img\adc-dac.png" width="250" height="auto">

This is pretty obvious and self explanatory. Daisy has a few pins that talk to plugdata via the blocks `adc~` and `dac~`.

ADC stands for Analog to Digital Converter = this is the input, e.g. microphone, another synth, ...
DAC stands for Digital to Analog converter = this is the output, e.g. a line out, headphones, ...

## What it looks like: most common is to use Mono/TS or Stereo/TRS jacks.

![Green Thonkiconn Stereo 3.5mm Audio Jacks (PJ366ST)](img\Green-Thonkiconns-stereo.jpg)
<sub>Green Thonkiconn Stereo 3.5mm Audio Jacks (PJ366ST)</sub>

![Thonk mono 3.5mm Audio Jacks (PJ301BM)](img\thonk_mono.jpg)
<sub>Thonk mono 3.5mm Audio Jacks (PJ301BM)</sub>

![Tip Ring Sleeve audio phone jacks](img\tip_ring_sleeve_ts_trs.png)
<sub>more info in the full [Wikipedia article](https://en.wikipedia.org/wiki/Phone_connector_(audio))</sub>

### TS - TRS 

These letters stand for Tip, Ring, and Sleeve.
And they refer to the parts of the jack plug that the different conductors are connected to. A TRS cable has three conductors vs. the two on a standard guitar cable, TS, or mono.

Looking at the plug or jack input socket on a device may not show clearly how many wires it will connect. On jacks this is more obvious, you can count the parts.

Looking at your components might give you some clue, the stereo mostly has a clear extra pin vs the mono.

## Pins 16 - 19

There are 2 stereo input pins: 16 and 17;
and 2 stereo output pins, 18 and 19.

Note the pin numbers here stand for the Pins on the Daisy board - if you need an oversight of pins you can [look at this spreadsheet](https://docs.google.com/spreadsheets/d/1xtg_s1tk8tm-6qNkBLFc6V1L_Mpmu-PCOvv7qEyr9mU/edit?usp=sharing).

You'll connect these to audio jack(s). And then you'll also connect ground to your jacks.

If you only need mono sound you only connect 1 of each as needed.

When using the Synthux Simple boards it will depend on which version you have whether you can connect a stereo or mono jack.

On e.g. the Simple Touch board the connections between the jacks and the Daisy board are already in place. Check the docs of your Simple board to see wether you've got this pre-configured and whether your jacks are mono or stereo.

The common multi footprint of the Simple board connectors will allow for a mono jack. You could 'hack' the extra pin by connecting an extra wire to another free pin.

## Components json setup

In the json file the header in the file contains the info.

If you select any of the preset json files for custom boards in the compile window they'll mostly all work as these are standard pins on the Daisy.

This json file would not have any working components. You'll just have a setup for audio. Without external controls. But if you would make a non interactive patch it would suffice:

```json
{
    "name": "myemptyboard",
    "som": "seed",
    "audio": {
        "channels": 2
    },
}

```
## Plugdata example

Together with a pd patch that just connects adc~ to dac~ the json file above would send audio straight from input to output.

<img src="img\adc-dac.png" width="150" height="auto">

## links / references / sources

TODO: insert Link to Synthux documentation.

[Link to table overview of all pins](https://docs.google.com/spreadsheets/d/1xtg_s1tk8tm-6qNkBLFc6V1L_Mpmu-PCOvv7qEyr9mU/edit?usp=sharing) 

[Thonk shopping website - jacks](https://www.thonk.co.uk/shop/3-5mm-jacks/)
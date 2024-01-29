---
layout: default
title: Encoders
nav_order: 16
parent: Components Plugdata examples
---

# Encoders

{: .highlight }
> 💡 This page isn't set up yet / in draft mode.

This could be considered an advanced part compared to connecting a regular potentiometer knob. 

{: .highlight}
> The Synthux simple boards main multi connectors cannot fit an encoder. You could use the free disconnected grid, or mount it elsewhere and connect the wires to the pcb that way.

An encoder typically has a VCC and GND plus 3 more pins. However, there are also encoders with only 3 pins.

Encoders are not like an analog potentiometer that has a linear set of values from 0 to 1.

Encoders send a series of clicks to tell which direction and how much you are turning it. 

Often encoders will also include a pushbutton function.

Hence why some have another pin configuration.



Template structure for parts:
  1. Name
  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources
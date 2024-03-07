---
layout: default
title: LED's
nav_order: 12
parent: Components Plugdata examples
---

# LED's - light emitting diodes

The little lights that can enhance the user experience; or just brighten the day.

## function - what can it do

A type of diode that illuminates when you pass power through it. The electricity will only flow in one direction. Take a small 3.3V coin cell and attach the LED, flip it around and you'll see this: one way it works, the other way round it doesn't.

<img src="img\ledCoincell.svg" width="150" height="auto">

### To fade or not to fade.

Simplest thing is to just turn the LED on or off. However it's also possible to use fading or making the led's less bright.

To fully understand this you could dive deep in how LED's work or you could look up the history of developing the infamous blue LED, but lets keep it at the basics here.

After you've connected the LED (see pins - section below), you'll program the LED to get powered On or Off, do this fast enough and you could create the illusion of fading.

### Fading - PWM

To create a difference in brightness ideally you control the amount of electricity that flows through it. So less voltage would result in less brightness.
If a pin like on many micro-controllers can only output a steady 3V or 5V, there is a way to still achieve this, called ***Pulse Wave Modulation (PWM)***. By quickly turning the led on and off, faster than the human eye can see, we can create the 'illusion' of more or less brightness.

For Plugdata this means that when we've setup the hardware and custom json file to use the PWM approach we can simply send a value between 0 and 1 to achieve brightness. Animate this change and we'll achieve fading.

## What it looks like

### One color LED

A one color LED has two legs, an anode and a cathode.

The longer leg is usually the anode connecting to power, the shorter leg the cathode and will connect to ground.

### RGB LED

RGB LED's have four legs, one for each color and one pin.

I think you'll mostly come across the common cathode RGB LED, however search for "RGB LED Common Cathode versus Common Anode" and you'll find many confused souls.

For the common cathode RGB LED you need to wire up each R, G, B, pin with a resistor to a pin on the microcontroller, the common ground goes straight to ground. So take in mind that an RGB LED will 'cost' you 3 pins.

### Expanding the number of controllable PWM pins

Using an extra chip, e.g. PCA9685, like done on some of the Electro-Smith devices (Patch, Petal), is probably the best way.
There is a breakoutboard by adafruit that connects over i2c, however, I've not tried hooking this up myself, so can't provide full guidance. [Look at the json files of json2daisy](https://github.com/electro-smith/json2daisy/tree/f77c6b40b95372643616dbef445e760998aacf33/src/json2daisy/resources), e.g. the main component_defs.json and the board specific json files for The Patch and PPetal, you'll find the code used for those. Look for words LED and the chip PCA9685.

## Pins - wiring up the LED's

For the sake of demoing, we'll be using single color LED's. These have a shorter leg, the cathode that needs to be connected to ground and the longer leg that goes through a resistor, 22O ohm, into the Daisy.

Todo: Which pins can do PWM?

I started using Digital 3V3 as power after I got a comment over at Synthux (⁠synthux.academy⁠), but there seems to be a clear disadvantage using the LED connected with the ground/cathode to the pwm pins. The video is also showing some flicker due to my phone camera's shutter speed, but the fading of the LED is really smooth for the second one.


Template structure for parts:
  1. Name
  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources
  https://github.com/electro-smith/json2daisy/blob/f77c6b40b95372643616dbef445e760998aacf33/src/json2daisy/resources/component_defs.json#L179
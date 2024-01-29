---
layout: default
title: Toggle switches and buttons
nav_order: 11
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

# Toggle switches and buttons

![toggle switches on Synthux Simple Touch](img\toggle_switch_on_synthuxSimpleTouch.jpg)

From discord by jonwtr:
> They look the same, but one has two positions, on/on the other has three clicks on/off/on. So they are the same as a button. Difference being that they remain in position. 
I just meant, toggle/switch versus a button, in that way. For a noob it may not be obvious that they're the same.

## Name

Button, switch, toggle switch,  they all refer to the same principle of having one connection and changing its state.

So in stores you'll find hundreds of types and names.

A good idea to start is with the terms ON-OFF and then see which configuration fits your needs.

## function - what can it do

The SPDT ON-ON and ON-OFF-ON LOOK the same, have the same 3 pins. But the mechanical difference is that one flips from left to right, and the other also stops in the middle.

ON - ON will send either the left or right pin as 'active'.

ON - OFF - ON Does the same, however it's middle position is disconnected from either side.

In Plugdata we can use the info of releasing a button or toggle as well.

That means while the ON-OFF-ON toggle is only connected to two pins, we can use it to toggle between 3 states or 3 different functions. E.g. 3 octaves, 3 wave forms, ...

{: .highlight}
> For debugging purposes, or just learning what positions or messages you're sending by moving or pushing the button/switch, it can be handy or necessary to learn how to print to serial.

<details open markdown="block">
  <summary>
    Printing to serial instructions</summary>
To be able to read messages sent by our components we can send it to print. Like with an Arduino this would be the function `Serial.print()`.

Steps to follow:
- In Plugdata you connect your component to a print object.
- When compiling you activate the serial debugging via USB
- connect to a serial monitor
  - If you have already setup Arduino you can use it's serial monitor.
[More info at its own page.](01_install_setup_plugdata\04_serial\serial_debug_print.md)
</details>

## what it looks like

![toggle switches Synthux Simple Touch 3sounds](img/toggleswitchesSynthuxSimplTouch3sounds.mp4)

For Plugdata or Daisy, the type of button or toggle doesn't matter. We just need to now what signal they send in which position.

The toggle switches one that are in the Synthux kits look like the red ones in the picture above.

There are also slider toggle types, rocker types, like the light switch on your walls, there are push button versions that remain in position when clicked and released when clicked again. There are momentary buttons, there those with built in LED's. It's endless.

You'll want to verify the datasheet of the parts to learn what type it is. Often by just looking at the part it may not be obvious.

Some toggles will just be a way of breaking or connecting one wire.

![Thonk toggle switches](img/switches-pcb-mount.jpg)
<sub>image from [Thonk shop](https://www.thonk.co.uk/shop/sub-mini-toggle-switches/)</sub>



## Pins

Both the ON-ON and the ON-OFF-ON Toggle switches have 3 pins.
- Both the outer pins should connect to a digital pin on the Daisy.
- The middle pin connects to ground

Don't forget there are two GND points on the Daisy that you should connect outside the board. In Synthux Simple Touch this is done in  the PCB itself when installing it. On other Simple boards this will also be included in the instructions. 

## Components json



## PD example(s)

### ON OFF ON - 3 options examples

#### Using the object `[spigot]`

![on_off_on_switch-3options_spigot](img/on_off_on_switch-3options_spigot.png)

Download this pd example: [on_off_on_switch-3options_spigot.pd](on_off_on_switch-3options_spigot.pd)

#### Using a signal flow

![on_off_on_switch-3options_signal](img/on_off_on_switch-3options_signal.png)

Download this pd example: [on_off_on_switch-3options_signal.pd](on_off_on_switch-3options_signal.pd)


## links / references / sources


***

Template structure for parts:
  1. Name
  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources
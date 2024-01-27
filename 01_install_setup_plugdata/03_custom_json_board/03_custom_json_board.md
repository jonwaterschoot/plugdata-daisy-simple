---
layout: default
title: Setting up a custom json
nav_order: 4
parent: Installation and setting up Plugdata with Daisy
---
# Setting up a custom json file to describe your daisy pin setup

There's a [Guide for pd2dsy](https://forum.electro-smith.com/t/quick-guide-on-setting-up-a-custom-json-file-for-pd2dsy-oopsy/4021) by Takumi Ogata on the Daisy forum.

As we're compiling from Plugdata the workflow is quasi the same. But just a bit easier as we do the compile process from within Plugdata. We do need to make a separate file that we select in the compile window: the custom json. And that has to follow the same principles.

{: .attention }
> The Heavy compiler will output an error when there are spaces in the path or in the file names. This also aplies to any subpatches you might use, or if you are exporting you're compiled patch to disk. 
>
> {: .warning }
> - Do not use spaces in file names or in the paths
> - Do not use capital letters in your custom components names

## Custom json for a custom Daisy setup

The custom json file will be used in the compile screen where we select it as our custom board under “Target board”.

There are already some board configurations available in the presets, e.g. Electrosmith's own Pod, Patch(init), there's also a Synthux Simple board.

On this page we'll use the Synthux Simple PCB as the example. Note that your build doesn't need to use the exact naming of the components, the custom json can have any name.

1. We make a custom json file (you can do this in a text editor)
2. In this file we tell the compiler to which pins our components are connected.
3. We specify what kind of component we're using (fader, switch, ...)

***

```json
example components
```
Link to Daisy Github going over the components and types
***

## Pin numbers

Pin numbers can become confusing, therefor I've made this overview.

![Pins Table overview](img\Pins-Table_overview_Daisy_plugdata.png)

[Link to spreadsheet](https://docs.google.com/spreadsheets/d/1xtg_s1tk8tm-6qNkBLFc6V1L_Mpmu-PCOvv7qEyr9mU/edit?usp=sharing) showing the pin numbers used in on the Daisy board, Plugdata, Synthux, ...

When you're making your own board it can be a handy tool to make your own copy and list your own connections and custom names.

***

Here's a piece of the [linked table](https://docs.google.com/spreadsheets/d/1xtg_s1tk8tm-6qNkBLFc6V1L_Mpmu-PCOvv7qEyr9mU/edit?usp=sharing) with the pins of the Simple Touch as an example:

|Daisy seed pin numbers on the board|Daisy pin names digital|Daisy pin names analog|Pin names Synthux|Pin numbers for Simple Touch to use in Plugdata|Simple touch mpr121 Description|Custom names in my custom json see my notes here:|
|:----|:----|:----|:----|:----|:----|:----|
|7|D6| |S07|6|switch vert down|toggle2down|
|8|D7| |S08|7|switch vert up|toggle2up|
|9|D8| |S09|8|switch hor left|toggle1left|
|10|D9| |S10|9|switch hor right|toggle1right|
| | | | | | | |
|20|A GND|A GND|A GND| |A GND| |
|21|3V3 Analog|3V3 Analog|3V3 Analog| |3V3 Analog| |
|22|D15|A0|S30|15|pot 0 bottom left|knob0|
|23|D16|A1|S31|16|pot 1 top left|knob1|
|24|D17|A2|S32|17|pot 2 top|knob2|
|25|D18|A3|S33|18|pot 3 top|knob3|
|26|D19|A4|S34|19|pot 4 top right|knob4|
|27|D20|A5|S35|20|pot 5 bottom right|knob5|
|28|D21|A6|S36|21|fader left|faderleft|
|29|D22|A7|S37|22|fader right|faderright|
|30|D23|A8| |23| | |
|31|D24|A9| | | | |
			

***

Synthux is using the ‘S’ number as a way to refer to the connections on their PCB. This is convenient for them to allow easy mounting of the Daisy on the back of the Simple PCB.

***

callouts:
  note:
    color: grey-dk
  attention:
    color: grey-lt    
  highlight:
    color: yellow
  warning:
    color: red
  new:
    color: green

{: .note }
A paragraph is a note

{: .attention }
A paragraph is a note

{: .highlight }
A paragraph is highlighted

{: .warning }
A paragraph is important

{: .new }
A paragraph is new

> {: .new }
> > A paragraph
> >
> > Another paragraph
> >
> > The last paragraph

{: .note }
> {: .opaque }
> <div markdown="block">
> {: .warning }
> A paragraph
> </div>

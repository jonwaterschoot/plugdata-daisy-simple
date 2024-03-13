---
layout: default
title: Setting up a custom json
nav_order: 4
parent: Installation and setting up Plugdata with Daisy
---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Setting up a custom json file to describe your daisy pin setup

## How is your hardware setup?

It's not easy to provide a general custom json, as that's mostly not going to be the same setup as your unique build.

For some general boards and devices there are presets available that you can select from the compile menu.

When setting up your own device, you'll most likely start with a breadboarded or a kit like those from Synthux.

Even if you plan to skip going the cpp / arduino route and start learning here it might be worthed to watch the build guides, as they proviidde some guidance in how to solder and how to connect.

{: .new}
> These basics are maybe enough to get you started:
>
>- ***connect Analog Ground AGND and Digital Ground DGND***
>   - Synthux pcb's have shortcuts for this
>
>- depending on wether you have mono or stereo in and outputs, connect your jacks accordingly
>
>- use the Daisy seed pinout diagram to look up which pins you can use for your components (e.g. analog for potentiometers)
    - most pages here each show the pins you can use, or [link to a spreadsheet]() that I made
> 

![Synthux Simple](img\Synthux_Simple_Daisy.jpg)
<sub>So you've connected some potentiometers on the Synthux Simple matrix to the analog pins of the Daisy, now what? (picture from Synthux)</sub>

There already exists a comprehensive [guide for pd2dsy](https://forum.electro-smith.com/t/quick-guide-on-setting-up-a-custom-json-file-for-pd2dsy-oopsy/4021) by Takumi Ogata on the Daisy forum.

And although we're compiling from Plugdata, the workflow is quasi the same. Even better, everything is just a bit easier as we do the compile process from within Plugdata. We do however need to make a separate file that we select in the compile window: **the custom json**. And that has to follow the same principles.

{: .new}
> As a recap, the Plugdata to Daisy workflow:
> - connect/solder components to the correct Daisy board pins
> - setup a json file that tells the compiler which pins are used
> - make a patch in Plugdata with your new custom setup
> - uploading your code to the board is done by compiling: 
>   - Heavy Compiler Collection (hvcc) helps converting your code to C++


{: .attention }
> The Heavy compiler will output an error when there are spaces in the path or in the file names. This also applies to any subpatches you might use, or if you are exporting/saving your compiled patch to disk. 
>
> {: .warning }
> ***Do not*** use spaces in file names or in the paths, ***do not*** use capital letters in your custom components names


## Custom json for a custom Daisy setup

The custom json file will be used in the compile screen where we select it as our custom board under “Target board”.

There are already some board configurations available in the presets, e.g. Electrosmith's own Pod, Patch(init), there's also a Synthux Simple board.

In this websites examples we'll use the Synthux Simple PCB pins. Note that your build doesn't need to use the exact naming of the components, the custom json can have any name.

{: .new }
> Custom naming:
> - You can name your knobs etc. how you want, just don't use CAPS or spaces.
>   - it could be `myfatfilter` instead of `knob1` 
> - You can choose a custom name for your board
> - You can choose the filename of the custom json
>   - again no spaces!

1. We make a custom json file (you can do this in a text editor)
2. In this file we tell the compiler to which pins our components are connected.
3. We specify what kind of component we're using (fader, switch, ...)

***

Here's a basic file with a few components setup.

```json
{
   "name": "myCustomDaisySynthFX",
   "som": "seed",
   "audio": {
     "channels": 2
   },

   "components": {
       "faderleft": {
           "component": "AnalogControl",
           "pin": 21
       },
       "knob1": {
           "component": "AnalogControl",
           "pin": 16
       },
       "toggle2up": {
           "component": "Switch",
           "pin": 7
       },
       "toggle2down": {
           "component": "Switch",
           "pin": 6
       },
       "recled": {
           "component": "Led",
           "pin": 23
       }


   }
}
```

***

This file has some info at the top about our board.

E.g. the type of the connected board is a `seed`, as in Daisy Seed:

```json
   "som": "seed"
```

When using other types of things connected to the board, they get a separate section. E.g. a led driver or the MPR121 touch sensor.

```json
   "parents": {
     "mpr121_driver": {
       "component": "Mpr121"
       }
   }
```

And then follows a list with the components and their pin types in the section `"components": {`

e.g. the analog potentiometers like knobs and faders:
```json
       "faderleft": {
           "component": "AnalogControl",
           "pin": 21
       }
```


By listing this correctly the right setup for the type of pins will be setup for you.

If you've used Arduino's think of the term pullup resistor.

The Daisy seed has a few pins that can have multiple setups so we need to tell the hardware how to activate or handle them.

Therefore we need to verify the type of pin we need: e.g. for a potentiometer we need an Analog pin.

## Pin numbers

Pin numbers can become confusing, therefor I've made this overview table.

![Pins Table overview](img\Pins-Table_overview_Daisy_plugdata.png)

Follow this [link to the spreadsheet](https://docs.google.com/spreadsheets/d/1xtg_s1tk8tm-6qNkBLFc6V1L_Mpmu-PCOvv7qEyr9mU/edit?usp=sharing) showing the pin numbers used on/in the Daisy board, Plugdata, Synthux, ...

When you're making your own board it can be a handy tool to make your own copy and list your own connections and custom names.

***

Here's a part of that [linked table](https://docs.google.com/spreadsheets/d/1xtg_s1tk8tm-6qNkBLFc6V1L_Mpmu-PCOvv7qEyr9mU/edit?usp=sharing) with the pins of the Simple Touch and some custom setup as an example:

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
			

{: .highlight }
> Synthux is using the ‘S’ number as a way to refer to the connections on their PCB. This is convenient for allowing to easily mount the Daisy on the back of the Simple PCB.

## Types of components and the way they communicate

In the examples of the components in the next chapter you'll find the json instructions for each specific component.

![Simple components footprint](img\Simple_footprint_diagram_S-p-800.jpeg)
<sub>illustration from Synthux website</sub>

There's a full list made by Electrosmith with all the supported components and all the parameters and ways you can receive or send info from and to them. 

In Plugdata you will need things like `float` numbers, or you might need a `bang`, which is a trigger that activates something. 

For example, the standard message a toggle switch, which is basically a type of button, will send is a bang. However we also have the option to add something to our name of the switch so Daisy will send a different type of message. The Switch has the options `_fall` for when a pin gets disconnected. Or a `_press` function that will send a specific type of message, a float of either 0 or 1.

![Plugdata Toggle Switches _press _fall](img\PlugdataToggleSwitches_press_fall.png)

|Switch|---|Returns a bang on the signal's rising edge (i.e. when the switch is actuated).|
|:----|:----|:----|
|Switch|_press|Returns a float representing the current state (1 = pressed, 0 = not pressed)|
|Switch|_fall|Returns a bang on the signal's falling edge (i.e. when the switch is released).|

{: .highlight}
> Components can send different types of messages by adding strings to their names in plugdata.
> - See the full list on the [pd2dsy Github page](https://github.com/electro-smith/pd2dsy?tab=readme-ov-file#interacting-with-the-daisy-io)
> - In the examples on this site we'll demonstrate some of these

## Aliases

It is possible to refer to your components by using aliases which you setup in the json file.

See this excerpt of code that is used in [custom_json_example.json from pd2dsy on their Github](https://github.com/electro-smith/pd2dsy/blob/master/util/custom_json_example.json)

```json
      "aliases": {
        "gate": "gatein1",
        "gate1": "gatein1",
        "gate2": "gatein2",
        "cvout": "cvout1",
        "encswitch": "encoder_rise",
        "enp": "encoder_press",
        "press": "encoder_press",
        "knob": "knob1",
        "ctrl": "knob1",
        "ctrl1": "knob1",
        "ctrl2": "knob2",
        "ctrl3": "knob3",
        "ctrl4": "knob4"
      }
```

{: .attention}
> Note that for the encoder the `_rise` and `_press` have been added inside the json already, making them available in Plugdata by the alias.
>
> These details could help you make your patch more readable or clearly defined.

## Download / link / full example

Though you'll probably end up tweaking or writing your own, there are a few pre-made versions of the custom json files you can find. Two full examples are on the end of this page.

### pd2dsy

Though some stuff is slightly outdated compared to the workflow you get via Plugdata, many valuable info can be found here:

- The pure data to daisy - [pd2dsy](https://github.com/electro-smith/pd2dsy) section on Github contains lots of useful info on the different components and the massages they send or receive.

  - See also this same page at the Wiki over at [DaisyWiki / pd2dsy Guide](https://github.com/electro-smith/DaisyWiki/wiki/pd2dsy-Guide), you'll find more info over there.

- As linked above: [custom_json_example.json from pd2dsy on their Github](https://github.com/electro-smith/pd2dsy/blob/master/util/custom_json_example.json)

### json2daisy

The Utility for converting JSON board definitions into valid, libDaisy compatible C++ board support files for the Daisy platform.

You won't need this, as its not a separate tool, but there are some examples for the different Elecrosmith boards/configurations like Pod, Patch, Field, ...

[json2daisy resources on Github](https://github.com/electro-smith/json2daisy/tree/main/src/json2daisy/resources) has all the Electrosmith configurations.

### Simple.json (Synthux)

Full json file 'Simple' that is included in Plugdata can be [downloaded from Github](https://github.com/plugdata-team/plugdata-heavy-toolchain/blob/main/resources/simple.json)

Note:
This is the file from plugdata's Github but I've added Toggle Switches on pins 6 to 9 at the end:

```json
{
    "name": "Simple",
    "som": "seed",
    "defines": {
        "OOPSY_TARGET_HAS_MIDI_INPUT": 1
    },
    "audio": {
        "channels": 2
    },
    "components": {
        "knob1": {
            "component": "AnalogControl",
            "pin": 15
        },
        "knob2": {
            "component": "AnalogControl",
            "pin": 16
        },
        "knob3": {
            "component": "AnalogControl",
            "pin": 17
        },
        "knob4": {
            "component": "AnalogControl",
            "pin": 18
        },
        "knob5": {
            "component": "AnalogControl",
            "pin": 19
        },
        "knob6": {
            "component": "AnalogControl",
            "pin": 20
        },
        "knob7": {
            "component": "AnalogControl",
            "pin": 21
        },
        "knob8": {
            "component": "AnalogControl",
            "pin": 22
        },
        "knob9": {
            "component": "AnalogControl",
            "pin": 23
        },
        "knob10": {
            "component": "AnalogControl",
            "pin": 24
        },
        "knob11": {
            "component": "AnalogControl",
            "pin": 25
        },
        "knob12": {
            "component": "AnalogControl",
            "pin": 28
        },
        "toggle1left": {
           "component": "Switch",
           "pin": 8
       },
       "toggle1right": {
           "component": "Switch",
           "pin": 9
       },
       "toggle2up": {
           "component": "Switch",
           "pin": 7
       },
       "toggle2down": {
           "component": "Switch",
           "pin": 6
       }
    },
    "aliases": {
        "knob": "knob1"
    }
}
```
---

### Synthux Simple Touch - jonwtr - setting up MPR121 Touch Sensor

This is the version I'm using. Note that for this to work you have to edit the 'mother-file' because of a bug the pins are not setup correct. To change the main json definition file you can do this:

#### **Edit a part of the toolchain json** components definition file

To get a working mpr121 **edit a part of the toolchain json** components definition file / might get fixed

- This is not ‘normal’ and is supposed to work without the edit;
- this bug has been reported: **[Bug: mpr121 pin setup incorrect](https://github.com/electro-smith/json2daisy/issues/18)**

- currently the file in question is causing an error referring to wrong pins
    - mpr121 touch sensor is supported, however seems to give a pin error:
    - `Error c2daisy: 'pin_scl’`
- We need to edit the file that contains the mpr121 code and is located in the installed toolchain:
    - edit code in the json file `component_defs.json`
    - on my windows machine it’s here: `C:\Users\gebruiker\Documents\plugdata\Toolchain\usr\bin\Heavy\json2daisy\resources\component_defs.json`
- Change the first line `“map_init”`:
    - Note I’ve added a few extra lines to easily see where it’s located

```json
Original code:
--------------
"Mpr121": {
		"map_init": "daisy::Mpr121I2CTransport::Config {name}_config;\n    {name}_config.periph = {periph};\n    {name}_config.speed = {speed};\n    {name}_config.scl = som.GetPin({pin_scl});\n    {name}_config.sda = som.GetPin({pin_sda});\n    {name}_config.dev_addr = {address};\n    daisy::Mpr121I2C::Config {name}_main_conf;\n    {name}_main_conf.transport_config = {name}_config;\n    {name}_main_conf.touch_threshold = {touch_threshold};\n    {name}_main_conf.release_threshold = {release_threshold};\n    {name}.Init({name}_main_conf);",
		"typename": "daisy::Mpr121I2C",
		"direction": "in",
		"pin": "scl,sda",
```

delete the part referring to the pins in the “map_init” **line 558**, leave the line “pin” as is:

delete: `{name}_config.scl = som.GetPin({pin_scl});\n    {name}_config.sda = som.GetPin({pin_sda});\n`    

```json
Altered code:
-------------
"Mpr121": {
		"map_init": "daisy::Mpr121I2CTransport::Config {name}_config;\n    {name}_config.periph = {periph};\n    {name}_config.speed = {speed};\n     {name}_config.dev_addr = {address};\n    daisy::Mpr121I2C::Config {name}_main_conf;\n    {name}_main_conf.transport_config = {name}_config;\n    {name}_main_conf.touch_threshold = {touch_threshold};\n    {name}_main_conf.release_threshold = {release_threshold};\n    {name}.Init({name}_main_conf);",
		"typename": "daisy::Mpr121I2C",
		"direction": "in",
		"pin": "scl,sda",
```

This part `mpr121_driver` will now load correctly.

```json
{
   "name": "SimpleTouch",
   "som": "seed",
   "defines": {
    "OOPSY_TARGET_HAS_MIDI_INPUT": 1
   },
   "audio": {
     "channels": 2
   },

   "parents": {
     "mpr121_driver": {
       "component": "Mpr121"
       }
   },

    "components": {
       "faderleft": {
           "component": "AnalogControl",
           "pin": 21
       },
       "faderright": {
           "component": "AnalogControl",
           "pin": 22
       },
       "knob0": {
           "component": "AnalogControl",
           "pin": 15
       },
       "knob1": {
           "component": "AnalogControl",
           "pin": 16
       },
       "knob2": {
           "component": "AnalogControl",
           "pin": 17
       },
       "knob3": {
           "component": "AnalogControl",
           "pin": 18
         },
       "knob4": {
           "component": "AnalogControl",
           "pin": 19
       },
       "knob5": {
           "component": "AnalogControl",
           "pin": 20
       },
       "toggle1left": {
           "component": "Switch",
           "pin": 8
       },
       "toggle1right": {
           "component": "Switch",
           "pin": 9
       },
       "toggle2up": {
           "component": "Switch",
           "pin": 7
       },
       "toggle2down": {
           "component": "Switch",
           "pin": 6
       },
       "recled": {
        "component": "Led",
        "pin": 23
       },
       "noiseled": {
            "component": "Led",
            "pin": 24
    }
       
  }

}

```
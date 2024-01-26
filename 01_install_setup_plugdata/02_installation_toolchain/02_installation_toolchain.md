---
layout: default
title: Installing Plugdata and the toolchain
nav_order: 99
---

# [](#compiling_workflow)Compiling workflow

To get up and running you need to understand the basic workflow for getting your Patches from Plugdata compiled onto the Daisy seed microcontroler.

> In short:
> 1. Make a compatible Plugdata patch
> 2. Use the compile menu to upload to Daisy.
    - Heavy does the translating.

Plugdata makes this whole process very smooth as everything happens from within the software.

A method that was already made for converting regular pure data patches was made available by Electrosmith in the handy tool pd2dsy. This tool allows to take patches made in pd format and convert/upload them.

However Plugdata has a few advantages over doing this manually via pd2dsy:
- Installing the needed toolchain is done for you when opening the compile window
- when using Plugdata in "compile" mode you get instant feedback when something is not compatible by and autocomplete won't show unsupported objects.

> **Use compile mode in Plugdata**, you'll instantly see when you use incompatible objects.
>  - limitting the auto-complete to hvcc compatible objects;
>  - and giving warnings when you use in-compatible ones

# [](#installing-1)Installing instructions

Install Plugdata for your platform via the [Plugdata website](https://plugdata.org).

After completing the installation go to the compile menu via 'Menu > Compile'

The first time you open the compile window the program will automatically begin downloading the toolchain.

The download is a one time event, so once the toolchain has completed the download this window will always open instantly.

## About the toolchain and compiling

The toolchain is a collection of needed stuff to 'export' your patches into other formats, this could be straight to C++ or in our case it provides everything we need to compile it onto the Daisy seed.

> Note the following section is a blunt copy taken from Plugdata's documentation and was copied from Github on 26/01/2024

***
***
***

# Compilation and Integration with HVCC Compiler

## Overview

**plugdata** provides the additional functionality to compile your patches for various targets. The supported targets include:

- **C++ Code:** Generates C/C++ source code for use in other DSP projects.
- **Electro-Smith Daisy:** Compiles and flashes code onto a Daisy microcontroller board.
- **DPF Audio Plugin:** Creates an audio plugin for use in various plugin hosts.
- **Pd External:** Compiles your patch into a Pure Data external object, optimizing its performance.

WARNING: Ensure that the destination path for exporting code or plugin binaries does not contain any spaces.

## Compiled Mode

In the main plugdata menu, you'll find a toggle box labeled ***Compiled Mode***. This mode checks your patch for compliance with plugdata compilation tools. It uses the [Heavy hvcc compiler](https://wasted-audio.github.io/hvcc/docs/01.introduction.html#what-is-heavy), which is limited to a subset of Pure Data Vanilla objects.

***Compiled Mode*** identifies unsupported objects in your patch, posting a message to the console and providing auto-completion only for compatible objects. 

By downloading the compilation toolchain, the [Heavy hvcc compiler](https://wasted-audio.github.io/hvcc/docs/01.introduction.html#what-is-heavy) maintained by [Wasted Audio](https://wasted.audio/) will be installed, along with additional compilation utilities. hvcc can only generate code for a portion of the objects included with plugdata, which are a subset of the Pure Data Vanilla set of objects.

***Compiled Mode*** indicates if there are objects in your patch that cannot be used in a compiled patch by posting a message to the console, and outlining the object in question. The auto-completion in plugdata will also only provide compatible objects when this mode is activated.

<img width="145" alt="PlugData Compilation Mode - unsupported object" src="img/heavy_unsupported.png">

<sub>Object error indication when using an unsupported object in Compilation Mode</sub>

<img width="251" alt="PlugData Compilation Mode - unsupported object console warning" src="img/heavy_unsupported_warning.png">

<sub>Console error warning when using an unsupported object in Compilation Mode</sub>


## Compiling in plugdata

Selecting `Compile...` opens a window with compilation options for different modes, each with common and mode-specific configurations.

### General Configuration

![General Configuration](img/heavy_general_config.png)

Common fields in this section include:

- **Patch to export:** Choose the patch you wish to export.
- **Project Name (Optional):** Autofills with the patch's name.
- **Project Copyright (Optional):** Specify under one of the [common source licenses](https://spdx.org/licenses/).

### C++ Code

![C++ Code Configuration](img/heavy_cpp_menu.png)

In C++ Code mode, your plugdata patch is transpiled to generic C/C++ code. Adapt the raw code for specific applications. Learn more in the [official documentation](https://wasted-audio.github.io/hvcc/docs/05.c.html).

### Electro-Smith Daisy

![Daisy Configuration](img/heavy_daisy_menu.png)

Daisy mode allows running your patch on an embedded hardware device based on an STM32 microcontroller. Options include choosing a target board, export types (Source Code, Binary, Flash), enabling USB MIDI, and configuring patch size.

### DPF Audio Plugin

![Plugin Configuration](img/heavy_dpf_menu.png)

DPF mode exports self-contained versions of your patch in various formats (VST2, VST3, LV2, CLAP, JACK). Choose export type (Source Code, Binary) and plugin type (Effect, Instrument, Custom). Select plugin formats in the provided list.

### Pd External

![External Configuration](img/heavy_pdexternal_menu.png)

Export your patch as a Pd external for optimized performance. Choose export type (Binary or Source Code) and enable copying to the externals path.

Refer to the [official documentation](https://wasted-audio.github.io/hvcc/docs/03.gen.pdext.html) for more details on each export option.


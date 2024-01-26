---
layout: default
title: What is Plugdata
nav_order: 99
---

# What is Plugdata

From the [Plugdata website](https://plugdata.org/):

> A visual programming environment for audio experimentation, prototyping and education.
> Plugdata is a free/open-source visual programming environment based on pure-data. It is available for a wide range of operating systems, and can be used both as a standalone app, or as a VST3, LV2, CLAP or AU plugin.

> plugdata allows you to create and manipulate audio systems using visual elements, rather than writing code. Think of it as building with virtual blocks – simply connect them together to design your unique audio setups. It's a user-friendly and intuitive way to experiment with audio and programming.

## About visual / modular programming

Read this if you don’t know these terms: Pure Data, Plugdata, Pd, flavours, modular, visual programming. I've written a short intro on the concept.

> 💡 If you know what Plugdata is and how it’s different from Pure Data > skip this part.

### Pure Data

Pure Data goes back many years and was made as a tool to help artists create (interactive) sound. It uses a visual blocks structure, comparable to e.g. Scratch, a tool used to teach (kids) programming, you link pieces of code together where each block has a specific function in the whole.

![Pure Data example](img/puredata_example.png)

### Pure Data - “flavours”

> **Pure Data** (or just "Pd") is an open source visual programming language for multimedia. Pure Data is developed by Miller Puckette since 1996 and you can find it on [his official website](https://msp.ucsd.edu/) along with the official documentation and other related resources. This is the official "Pd" or "main distribution" and it is also known as "Pd Vanilla", but there are other forks or "flavours".

source: intro on puredata.info 


### The modular approach

There are many tools out there that use this approach to programming or building electronic stuff, be it analog or digital. In 3D software like e.g. Blender they’re called nodes, Touchdesigner and [Cables.gl](http://Cables.gl) are both examples of tools that heavily rely on the approach of connecting blocks with virtual cables.

You could go far with this analogy as all things are a whole of parts, yet for sake of this document let’s just keep the connecting of different parts as the main concept.

### Eurorack

Coming from the music world you might be familiar with modular Eurorack synths. Maybe you’ve even used synths or kits that use Daisy. Or maybe you’ve seen the virtual eurorack systems like VCV rack or Cherry Audio Voltage Modular and many others ([See some listed in this article on attackmagazine.](https://www.attackmagazine.com/reviews/the-best/ten-of-the-best-modular-software/) )

### VCV a virtual eurorack cable spaghetti maker:

  https://youtu.be/NPErDUlwSlg?list=PL7NZKetd80yrCyyQ2-1J8fad420gL8MAf

### Modular coding

Seeing you’ve stumbled upon this page, you’re probably already interested or knowledgeable on the concept of using code and libraries. I have been tinkering with Arduino microcontrollers before and most code I’ve used relied heavily on the work of others, not only the builders of the hardware and it’s software, but also people who’ve made pieces of code often called libraries that you refer to in your own piece of code. Or sometimes it’s just pieces you could copy paste at the bottom etc. …

  - So you can use links or refer to these pre-made pieces of functions and tools inside your own code that get compiled or run in the background.
    - E.g. case in point of this page referring to Daisy seed and the mpr121: you link to the mpr121 touch sensor, and in pure data all you need to do is refer to the touch points, without actually knowing how it works.
    - The necessary code to talk to the sensor, the code to read the sensor, and the implementation into plugdata is all being done through various tools, libraries.
    - As an end user we can just put a block that says “knob1”, etc.
  - Pure Data can be seen as a similar thing of being a modular programming approach you write names of functions or tools; e.g. an oscillator, you don’t know how the oscillator is itself in turn made of smaller components. You just put a block that says give me an oscillator with the frequency 440.
    - We don’t always have to know how to make paint, brushes and canvas to be a proficient painter

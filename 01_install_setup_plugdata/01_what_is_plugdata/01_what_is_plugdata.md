---
layout: default
title: What is Plugdata
nav_order: 2
parent: Installation and setting up Plugdata with Daisy
---

# What is Plugdata

From the [Plugdata website](https://plugdata.org/):

{: .note }
> A visual programming environment for audio experimentation, prototyping and education.
> Plugdata is a free/open-source visual programming environment based on pure-data. It is available for a wide range of operating systems, and can be used both as a standalone app, or as a VST3, LV2, CLAP or AU plugin.
>
> Plugdata allows you to create and manipulate audio systems using visual elements, rather than writing code. Think of it as building with virtual blocks – simply connect them together to design your unique audio setups. It's a user-friendly and intuitive way to experiment with audio and programming.

## About visual / modular programming

Read this if you don’t know these terms: Pure Data, Plugdata, Pd, flavours, modular, visual programming. I've written a short intro on the concept.

{: .highlight }
> 💡 If you know what Plugdata is and how it’s different from Pure Data > skip this part.

### Pure Data

Pure Data goes back many years and was made as a tool to help artists create (interactive) sound. It uses a visual blocks structure, comparable to e.g. Scratch, a tool used to teach (kids) programming, you link pieces of code together where each block has a specific function in the whole.

![Pure Data example](img/puredata_example.png)

### Pure Data - “flavours”

{: .note }
> **Pure Data** (or just "Pd") is an open source visual programming language for multimedia. Pure Data is developed by Miller Puckette since 1996 and you can find it on [his official website](https://msp.ucsd.edu/) along with the official documentation and other related resources. This is the official "Pd" or "main distribution" and it is also known as "Pd Vanilla", but there are other forks or "flavours".
>
> source: intro on puredata.info 


### The modular approach

There are many tools out there that use this approach to programming or building electronic stuff, be it analog or digital.

In 3D software like e.g. Blender they’re called nodes, Touchdesigner and [Cables.gl](http://Cables.gl) are both examples of tools that heavily rely on the approach of connecting blocks with virtual cables.

Maybe you've seen the DAW Bitwig and how the grid can be used to build your own effect or synth.

{: .attention }
> The common idea is using cables to connect pieces to interact.

You could go far with this analogy as **all things are a whole of parts**, yet for sake of this document let’s just keep the connecting of different parts as the main concept.

If you are guitar player or seen one then you've certainly seen them using pedals to add effects. These pedals are our objects in Plugdata, sometimes our patches are inside the pedal adding extra functions, **tweaking circuits**, other times we just **plug the pedal in without knowing it's inner magic**.

### Eurorack

Coming from the music world you might be familiar with modular Eurorack synths. Maybe you’ve even used synths or kits that use Daisy. Or maybe you’ve seen the virtual eurorack systems like VCV rack or Cherry Audio Voltage Modular and many others ([See some listed in this article on attackmagazine.](https://www.attackmagazine.com/reviews/the-best/ten-of-the-best-modular-software/) )

### VCV a virtual eurorack cable spaghetti maker:



  https://youtu.be/NPErDUlwSlg?list=PL7NZKetd80yrCyyQ2-1J8fad420gL8MAf

### *Modular* coding or patching

Seeing you’ve stumbled upon this page, you might already be familiar or knowledgeable on the concept of using code and libraries.

It's often a way to prevent us from reinventing the wheel. But also a huge help for starters as we don't need every piece of complex code, we can just reference a certain function that's easily accessible for us.

In Plugdata we'll use a block (object), with the word `myknob`, and through the use of several other files, when we save or rather compile to the Daisy microcontroller the software will use these behind the curtains info to write the correct code.

This gives two advantages:
- it's easy to use the functions it provides
- we keep our own code / patch clean and tidy making it easier to write and read

E.g. case in point of using Daisy seed and knob connected to one of the pins:
  1. We put a few lines in a separate file that describes our board and how it's connected (custom json)
  2. The necessary code to talk to the sensor, the code to read the sensor, and the implementation into Plugdata is all being done through various tools, libraries.
  3. As an end user we can just put a block that says “knob1”, etc.
 
   Plugdata can be seen as a similar thing of this modular programming approach you write names of functions or tools; e.g. an oscillator, you don’t know how the oscillator is itself in turn made of smaller components. You just put a block that says give me an oscillator with the frequency 440.

{: .new }
We don’t need to know how to make paint, brushes and a canvas to be a proficient painter. We use tools all the time that we couldn't build ourselves.

***
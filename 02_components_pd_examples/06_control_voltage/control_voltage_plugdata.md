---
layout: default
title: Control Voltage - CV
nav_order: 15
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

# Control Voltage - CV

How Daisy can send or receive CV signals over some of it's pins.

{: .highlight }
> 💡 This page isn't set up yet.

From Daisy forum, an [answer by Takumi Ogata](https://forum.electro-smith.com/t/is-there-a-resource-for-how-to-use-json-pin-names-when-using-pd2dsy/4005/6):

{: .note }
> The Daisy Seed outputs 0.0V-3.3V out of its DAC outputs. And on boards like the Daisy Patch, that signal is amplified to 0.0V-5.0V.
>
> The Daisy (unlike Arduino) has GPIO pins. So pin D20 can be analog input or even digital output. Also worth noting that, even if you decided to use pin D20 as analog A5, it doesn’t care if you’re using an analog component like potentiometer or digital component like a switch as long as the voltage coming in is 0.0V to 3.3V range.
>
> Cd4051 Multiplexer Tutorial Is Here! 6
>
> If you’re using DaisyDuino or .cpp, it’ll be easy: Let's Add 4+ More DACs/CVs with Quad DAC! (Also, I2C tips!)
For pd2dsy and Oopsy, I haven’t looked too deep into it.
> In general, a component like the MCP4922 is recommend for adding more DACs.

***

Template structure for parts:
  1. Name
  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources
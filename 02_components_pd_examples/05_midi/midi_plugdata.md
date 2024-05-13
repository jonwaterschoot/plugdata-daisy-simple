---
layout: default
title: Midi
nav_order: 14
parent: Components Plugdata examples
---

# Midi

{: .attention}
>**This Page isn't ready yet - Midi is unstable / experimental**
>Thus far I've been having mixed results with midi. Midi implementation between plugdata and Daisy is unstable, so please do not expect any results, th info here is merely what I've gathered up until now. Sometimes it works, often it crashes. 
>Do not expect official support for any of this. (while that goes for most of Plugdata-Daisy, the midi feature is known to be unstable.)
>
>It is possible to use **midi over USB** (note the option in the compile window)
>
>Connecting **midi via trs**: using the tx-rx pins is also possible, but this needs extra components / circuitry.

This diagram I have copied from one of the files shared by Electrosmith in the past, can't find the source atm.
![midi circuit for Daisy](img\midi_circuit_for_daisy_electro-smith.png)


***
I have connected the miditrs breakout board from Denki-oto to my Synthux Simple Touch.
The breakout board is 5v, using a logic level shifter, I was able to connect to the Daisy Tx Rx pins.
Apparently I had to connect Tx to Tx. I thought it would have been Tx to Rx ... 
I was able to receive and transmit midi now with a simple pd patch.
I had hoped to be able to power it through the power the daisy can receive over USB, but simply connecting the power to e.g. the VIN pin doesn't seem to work with the logic level shifter. So I'm powering it with a battery. Positive thing now is that I can now power my Simple touch standalone.
I've also learned that it is ok to have the Daisy connected to my computer, while also being connected to the power from the battery.
So no need to unplug it while testing / uploading new code.

Midi is sent and read from both the tx-rx pins and USB midi. In the future this might change.

- RX TX serial
    - the default midi pins are `usart1_rx` and `usart1_tx`

| 14 | D13 |  | USART1 Tx | I2C4 SCL | 14 | S14 | S35 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 15 | D14 |  | USART1 Rx | I2C4 SDA | 15 | S15 | S34 |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |  |

***


To do: Setup page according to sites template:

Template structure for parts:
  1. Name
  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources
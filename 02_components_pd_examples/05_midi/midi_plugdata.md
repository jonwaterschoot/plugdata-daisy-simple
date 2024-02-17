---
layout: default
title: Midi
nav_order: 14
parent: Components Plugdata examples
---

# Midi

USB - UART - TRS - ...

To do:

I'm going to try connecting the miditrs board (from denki-oto) to the Simple Touch. The mpr121 is already connected to SCL/SDA pins D11, D12, so I'd connect to the other two pins D14 and D15. Am I correct in this, and how do I 'teach' plugdata where the data is coming from/going to? 
D11	I2C1 SCL	UART4 Rx
D12	I2C1 SDA	UART4 Tx
D13	USART1 Tx	I2C4 SCL
D14	USART1 Rx	I2C4 SDA


Template structure for parts:
  1. Name
  2. function - what can it do
  3. what it looks like
  4. Pins
  5. Components json 
  6. PD example(s)
  7. links / references / sources
---
layout: default
title: Memory and CPU - custom linker
nav_order: 5
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

# Memory and CPU - custom linker

The Daisy has a few options for using different types of memory when uploading your compiled patch. You'll come across RAM, SRAM, QSPI, ...
Maybe you'll need some space to to save a sample. It's possible, yet pretty complex if you're new.

## Memory allocations and regions for e.g. using delayread

Specifically I started out with wanting to experiment with **delays**, and the `[delread]` object quickly fills up the memory of the Daisy when you want longer delays than 1 or 2 seconds. And I wanted a stereo delay, so that's double ...

That’s why I ended up using a custom linker to make us of makes use of SDRAM. Delays make use of this larger available memory. Though I’ve yet to learn more about how memory allocation actually flows, this seems like a good thing to know.

## More info at these links:

[GitHub - electro-smith/pd2dsy: Utility for converting Pure Data (Vanilla) patches to Daisy projects.](https://github.com/electro-smith/pd2dsy/tree/master?tab=readme-ov-file#--ram)

And this site 

[libDaisy: Getting Started - External SDRAM](https://electro-smith.github.io/libDaisy/md_doc_2md_2__a6___getting-_started-_external-_s_d_r_a_m.html)

To be able to use this larger memory I've been using the custom linker [sram_linker_sdram.lds](https://github.com/electro-smith/pd2dsy/blob/master/util/sram_linker_sdram.lds) found at the pd2dsy Github: 

[pd2dsy has the different linkers](https://github.com/electro-smith/pd2dsy/tree/master/util)

Saved the file on your computer and in the compile window choose this file with option ‘custom linker’ under `Patch size` 

- Also pick the corresponding `App type` option below that, I didn’t see it at first that I could scroll down!

![Custom linker SRAM](img/Custom_linker_sram.png)

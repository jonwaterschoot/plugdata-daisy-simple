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
[ ] Insert link to pin spreadsheet

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

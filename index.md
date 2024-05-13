---
layout: default
title: Home
nav_order: 1
---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>

# Get up and running with Plugdata and Daisy 
**(Get up and running with Plugdata and Daisy on your Synthux Simple pcb's)**

The goal is to give a starters guide for noobs wanting to learn how to connect and setup your own hardware with the software Plugdata.

The Plugdata approach has the capacity to be a bit more user friendly than going for the full-on coding method with e.g. Arduino or C++. But also has the potential to be your goto for larger projects.

![Plugdata Synthux Simple Touch example](01_install_setup_plugdata\01_what_is_plugdata\img\Simpletouch_soundscpr_plugdata_example.jpg)

{: .new}
>**Under construction note**
>
>Everything about this, Plugdata, Synthux, Daisy, HVCC, ... These are all pieces of a puzzle that are constantly evolving or might be in various stages of development. Hence depending on when you read this, things might have changed.
>
>This website/guide itself is heavily under construction. I welcome critique, help, copying, etc.

## The site is built around three main parts

 - **What is Plugdata**
   - A more informative general part.
 - **Installation and setup**
   - The essential / needed part.
 - **Examples for basic components with Plugdata**
   - The juicy stuff, what you'll jump to, even though you should learn to walk first.

{: .new}
> Use the menu / Table of content to quickly glance at this site's content. Left on larger screens / at the top for smaller screens
>
> On top of every page there should be a TOC for each particular page.

## For whom?

You're interested in programming your own synth, but;

If you are new or intimidated by programming and find writing your own C/C++ or Arduino code a cumbersome idea to learn, this might be your answer.

This site has info on the basic things you'll need to start building and programming a Synth and/or audio FX device.

## Watch these videos first, they'll make everything easier to digest here

This website contains a lot of text, each time I try to be coherent and complete, i end up with lengthy info. The videos made by Wasted Audio, the current maintainer of HVCC, are a good way to get insight into how the HVCC compiler works and how Plugdata is one of the ways that the compiler can help convert code.

<iframe width="560" height="315" src="https://www.youtube.com/embed/XKohpWGTKsQ?si=TPU_sbOkSPxXVzE8" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Watch this one next:

<iframe width="560" height="315" src="https://www.youtube.com/embed/-li27LeH4ZY?si=L-bVxzjuf8Tw0WZI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Skills needed

{: .new}
> TLDR; 
>
>Personally I think anyone with a basic knowledge on working with a computer, installing software etc. Would be able to do this, with enough commitment of course.

There are so many tutorials and courses to find on anything these days, so depending on your needs you might first want to learn more about Synthesis, or about how microcontrollers work, ...

My recent journey from Plugdata to Daisy came about through learning Synthux's Simple PCB's and the info and lessons they provide.

This is why I'm using the Synthux Simple boards in the examples on this site, but most will apply to anyone using Daisy Seed and Plugdata.

To sketch my basic skill-set:

I personally started tinkering with some basic Arduino's for art projects many years ago. I've dabbled in html and css, and some other basic web stuff like js etc ... And I used an early version of Fruity Loops in the 90's. I've been playing with graphical software and Blender (3D) for +20 years.

My renewed interest in music and synthesis is much younger and about the only upside to becoming disabled with chronic pain and being chained to a couch.

So, to conclude, I can use a computer pretty well, but, I'm still not very skilled at programming purely with a text based approach.

The visual programming of Plugdata is the ideal method for me, it's still programming, yet I find it more approachable to see the structure as a network of connected parts.

## This is a work in progress

{: .highlight}
> This website is not completed, at all ...

The main goal was to provide some working examples of Plugdata code that works with components like knobs and LEDs connected to the Daisy seed.

When a page is incomplete, or looks like a draft, it's exactly what it looks like. 🙈

## Why I made this

The origin of this website comes from joining [Synthux Academy](https://www.synthux.academy/) and learning about the option to use Plugdata to program Daisy seed.

As I was taking notes when I was trying to get up and running in Plugdata with a touch sensor + the Daisy seed, I started thinking about a repository with some basic examples for starters such as myself.

Right at the time as I was doing this, Synthux brought out the Simple Touch PCB, using the sensor I already had. When they then also launched the Synthmas challenge, I just had to join.

As I got praise for the project and the documentation I made, I felt even more motivated to start this site.

This was my submission:
[Soundscpr_alpha:](https://jonwtr.notion.site/Plugdata-and-daisy-seed-mpr121-touch-sensor-41be6a24dc0b4dc4bdd2fffbe4763dee) stereo audio input - drone synth - stereo delay - fx patch, made in Plugdata.

<style>
iframe {
  aspect-ratio: 16/9;
  width: 100%;
  max-width: 800px;
}
</style>
<iframe src="https://www.youtube.com/embed/cOXGNsUJmgU?si=b6_w6sTPkyfVucrS" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

[The Notion link to my submission](https://jonwtr.notion.site/Plugdata-and-daisy-seed-mpr121-touch-sensor-41be6a24dc0b4dc4bdd2fffbe4763dee) also contains the initial documentation I wrote that led to this whole website.

## From markdown to Github Pages

This site is built with markdown and gets published to a Github Pages website via the tool just-the-docs. Some internal links might not always work, but menus are auto generated and should always point to the correct pages.

This has also been a learning process for me, but has brought me some new knowledge on the Github workflow with vscode.

In the future I might try out a different template / setup. I've been looking into [MKdocs Material](https://github.com/squidfunk/mkdocs-material) I'm even considering using this to build my personal website/portfolio.

## Suggestions / Questions

This website is a one-man-who-is-pretty-much-a-noob, so I'll gladly welcome any criticism, remarks, etc. 

Maybe some better setup, other documentation template, ... 

Feel free to contact me @jonwtr on the Discord servers of Synthux, Plugdata or Daisy

Find my other contact info via my website, [www.jonwtr.be](https://www.jonwtr.be), the website I was supposed to set up instead of this one ...

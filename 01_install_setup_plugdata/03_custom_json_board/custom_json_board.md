---
layout: default
title: Setting up a custom json
nav_order: 99
---
# Setting up a custom json file to describe your daisy pin setup

callouts:
  highlight:
    color: yellow
  important:
    title: Important
    color: blue
  new:
    title: New
    color: green
  note:
    title: Note
    color: purple
  warning:
    title: Warning
    color: red


{: .highlight }
A paragraph is highlight

{: .important }
A paragraph

{: .new }
A paragraph is new

{: .note }
A paragraph is note

{: .warning }
A paragraph is warning



{: .note-title }
> My note title is NOTE
>
> A paragraph with a custom title callout

{: .important }
> A paragraph
>
> Another paragraph
>
> The last paragraph

{: .important-title }
> My important title
>
> A paragraph
>
> Another paragraph
>
> The last paragraph

> {: .new }
> > A paragraph
> >
> > Another paragraph
> >
> > The last paragraph

{: .important }
> {: .opaque }
> <div markdown="block">
> {: .warning }
> A paragraph
> </div>

---
title: README - Demonstrating a simple dashboard layout with CSS Grid
author: Patrick Hall
---

# README - Demonstrating a simple dashboard layout with CSS Grid

This repository demonstrates a simple dashboard layout using CSS Grid. The goal was to use as little `CSS` as possible to create a dashboard layout with internal scrollable panes.

To add some random content, and for fun, I implemented a simple Wikipedia article viewer that loads articles via the Wikipedia API. In many cases the article will be longer than the `<main>` element’s height, and thus scrolling will be activated. For longer articles with many sections, the dynamic table of contents in the `<aside>` will also scroll.

Here’s an example of a long article:

<https://amundo.github.io/dashboard-layout/#CSS>

In this case both the `<main>` and `<aside>` elements are scrollable.

Most articles will be like this one, where the content is scrollable but the table of contents (`<aside>`) is not:

<https://amundo.github.io/dashboard-layout/#John_F._Ficken>

If the article is very short there might be no scrolling at all

<https://amundo.github.io/dashboard-layout/#Log_Cabin_Stable>


## `CSS` outline

The basic premise here is encapsulated in these lines:

```css

html, body  { height: 100%; }
aside, main { overflow-y: scroll; }
body {
  display: grid;
  grid-template: 
    "header header" auto 
    "aside  main"   1fr 
    "footer footer" auto 
  /  1fr    3fr;
  header, footer {
    grid-column: span 2;
  }
}
```


---
title: Splitting Words
description: Splitting Words using CSS(SCSS)
date: 2021-04-21
draft: false
slug: /pensieve/splitting-words
tags:
  - Theming
  - CSS
---

[Codepen Demo](https://codepen.io/bhargavborse/pen/MWvxyov)

## CSS [SCSS]

```css
.splitting .char {
  animation: slide-in 1s cubic-bezier(.3, 0, .3, 1) both;
  animation-delay: calc(60ms * var(--char-index));
  color: saturate(lighten(#182952, 55%), 60%);
}

@keyframes slide-in { 
  from {
    transform: translateY(1em);
    opacity: 0;
  }
}
```

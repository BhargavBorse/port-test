---
title: Loading
description: Loading animation for the page
date: 2019-12-03
draft: false
slug: /pensieve/loading
tags:
	- Loading Animation
---

[Codepen Demo](https://codepen.io/bhargavborse/pen/RwZqEMm)

## HTML [PUG]

```html
h1(data-text="Loading...") Loading...
```

## CSS [SCSS]

```css
body{
	font-family: Lato, sans-serif;
	
}

h1{
	margin: 0;
	padding: 0;
	text-transform: uppercase;
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
	font-size: 5em;
	color: #f5f5f5;
	letter-spacing: 5px;
	
	&:before{
		content: attr(data-text);
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		color: #000;
		overflow: hidden;
		animation: animate 10s linear infinite;
		border-right: 3px solid #000;
	}
}

@keyframes animate
{
	0%{
		width: 0;
	}
	50%{
		width: 100%;
	}
	100%{
		width: 0;
	}
}
```

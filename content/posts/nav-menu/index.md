---
title: Nav Menu Animation
description: A simple animation for the nav menu bar
date: 2021-04-21
draft: false
slug: /pensieve/nav-menu
tags:
  - Theming
  - Nav Bar
---

[Codepen Demo](https://codepen.io/bhargavborse/pen/KKvrbLv)

## HTML

```html pug
.sidebar
	ul
		li
			a(href="#") Home
		li
			a(href="#") About
		li
			a(href="#") Services
		li
			a(href="#") Portfolio
		li
			a(href="#") Contact
	button.sidebar-btn
		span
```

## CSS Variables

```css scss
body{
	margin: 0;
	padding: 0;
	font-family: Lato, sans-serif
}

.sidebar{
	position: fixed;
	top: 0;
	left: -250px;
	height: 100%;
	width: 250px;
	background: #262626;
	transition: .5s;
	
	&-btn{
		position: absolute;
		top: 0;
		right: -50px;
		width: 50px;
		height: 50px;
		outline: none;
		border: none;
		background: transparent;
		cursor: pointer;
		box-sizing: border-box;
		
		span{
			width: 35px;
			height: 3px;
			background: #262626;
			position: absolute;
			top: 20px;
			
			&:before, 
			&:after{
				content: '';
				width: 35px;
				height: 3px;
				background: #262626;
				position: absolute;
				left: 0;
				transition: .5s;
			}
			
			&:before{
				top: -10px;
			}
			&:after{
				top: 10px;
			}
		}
	}
}

ul{
	margin: 0;
	padding: 20px 0;
	
	li{
		list-style: none;
	}
}

a{
	color: #fff;
	font-size: 1.3em;
	text-decoration: none;
	display: block;
	padding: 10px 20px;
	border-bottom: 1px solid rgba(0,0,0, .2);
	transition: .5;
	
	&:hover{
		transition: .3s;
		color: lightblue;
	}
}

.active{
	transition: .5s;
	left: 0;
}

.toggle span{
	background: transparent;
	
	&:before{
		top: 0;
		transform: rotate(45deg);
		transition: .5s;
	}
	&:after{
		top: 0;
		transform: rotate(-45deg);
		transition: .5s;
	}
}
```

## JavaScript

```js:title=app.js
$('.sidebar-btn').click( () => {
	$('.sidebar').toggleClass('active');
	$('.sidebar-btn').toggleClass('toggle');
});
```
---
title: Checkout Form
description: Checkout Form with focus on the fields while filling out the form
date: 2021-04-21
draft: false
slug: /pensieve/checkout-form
tags:
  - Theming
  - Forms
---

[Codepen Demo](https://codepen.io/bhargavborse/pen/jOLJqWr)

## HTML

```html
<form action="">
  <div class="module email">
    <label>
      <span class="number">1</span>
      <span class="text">Email</span>
    </label>
    <div class="module__content">
      <input type="text" placeholder="email">
    </div>
  </div>

  <div class="module shipping">
    <label>
      <span class="number">2</span>
      <span class="text">Shipping</span>
    </label>
    <div class="module__content">
      <div class="row">
        <input type="text" placeholder="First">
        <input type="text" placeholder="Last">
      </div>
      <div class="row">
        <input type="text" placeholder="Address Line 1">
      </div>
      <div class="row">
        <input type="text" placeholder="Address Line 2">
      </div>
      <div class="row">
        <input type="text" placeholder="City">
        <input type="text" placeholder="State">
        <input type="text" placeholder="Zip">
      </div>
      <div class="row">
        <input type="text" placeholder="Phone Number">
      </div>
    </div>
  </div>
</form>
```

## CSS Variables

```css scss
body {
  font-family: sans-serif;
}

$numSize: 30px;
$numBorder: 2px;

form {
  .module {
    display: flex;
    flex-direction: column;
    max-width: 400px;
    padding: 20px;
    background: #eee;
    margin-bottom: 20px;
    transition: all 0.25s ease;
    &.active {
      background: lightblue;
      padding: 30px 20px;
      input {
        height: 30px;
        border-color: grey;
      }
    }
    &__content {
      margin-left: calc(#{$numSize} + #{$numBorder} + #{$numBorder} + 10px);
    }
    label {
      display: flex;
      align-items: center;
      margin-bottom: 10px;
      font-weight: 700;
      .number {
        width: $numSize;
        height: $numSize;
        border: $numBorder solid black;
        border-radius: 100%;
        display: inline-block;
        display: flex;
        justify-content: center;
        align-items: center;
        margin-right: 10px;
        font-size: 16px;
      }
    }
    input {
      // width: fit-content;
      width: 100%;
      outline: none;
      border: none;
      background: transparent;
      margin-bottom: 10px;
      font-size: 16px;
      transition: all 0.25s ease;
      border-bottom: 1px solid #ccc;
      &:hover {
        border-color: grey;
      }
    }
  }
}

.row {
  display: flex;
  & > * {
    margin-right: 10px;
  }
}

```

## JavaScript

```js
const inputs = document.querySelectorAll(".module input");

inputs.forEach(input => {
  input.addEventListener("focusin", function() {
    this.closest(".module").classList.add("active");
  });
  input.addEventListener("focusout", function() {
    this.closest(".module").classList.remove("active");
  });
});

```
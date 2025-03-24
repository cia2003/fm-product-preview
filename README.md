# Frontend Mentor - Product preview card component solution

This is a solution to the [Product preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/product-preview-card-component-GO7UmttRfa). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover and focus states for interactive elements

### Screenshot

- Desktop Screenshot:
<img src="/screenshots/desktop_ss.png" width="500px" height="300px" object-fit="cover">

- Mobile Screenshot:
<img src="/screenshots/mobile_ss.png" width="375px" height="800px" object-fit="cover">

### Links

- [Solution URL](https://github.com/cia2003/fm-product-preview)
- [Live Site URL](#)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox

### What I learned

Yep, here we go:

I learned how to use two pictures with different sizes on a certain screen. With Javascript, we can manipulate the document and change the source of the image tag. But, how do we solve this without Javascript?

There are two approaches of how to solve this:
1. Using two image tags.
This approaches quite simple: you directly set two image tags and set its sources. 

For example like this:

```html
<img class="product__img-desktop" src="/your_file/desktop_img.png" alt="Image for desktop screen">
<img class="product__img-mobile" src="/your_file/mobile_img.png" alt="Image for mobile screen">  
```
Then, you can display or hide the image tag as needed in CSS. For example, I want to hide the mobile image so that it can only display the desktop image and vice versa in smaller screen:

```css
/* Other codes */
.product__img-mobile {
  display: none;
  /* other codes */
}

@media screen and (max-width: 425px) {
  .product__img-desktop {
    display: none;
  }
  .product__img-mobile {
    display: block
  }
}
```

2. Using one div tag and set the image as a background.
Welp, I am just experimenting and treating the div tag as an image. Usually, if you set the image as a background, you can add a words or something upon the image. Because I treat it only as an image (as I say before), I just set the background with the image URL. Then, I can change the URL depend of the screen.

```css
.product__img {
    background-image: url('/your_file/desktop_img.png');
    background-size: contain;
    background-repeat: no-repeat;
    aspect-ratio: 2/3;
    border-radius: 10px 0 0 10px;
}

@media screen and (max-width: 767px){
    .product__img {
        background-image: url('/your_file/mobile_img.png');
        aspect-ratio: 5.45/3.82;
        border-radius: 10px 10px 0 0;
    }
}
```
I set the `background-size` to `contain`so that all part of the image will be shown without being stretched. To prevent the image from being repeated, you can set the `background-size` to `no-repeat`.

The problem start here, you can see some large space between the image and the letter. How to reduce it? Use `aspect-ratio`.

### Continued development

While I still try to learn BEM Methodology and CSS Grid, I want to try a different approach for my workflow. Usually, I start to work for desktop first and later on mobile. For the next, I want to try mobile-first workflow and see the effectiveness.

### Useful resources

- [CSS Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS) - You can visit this documentation to enrich your knowledge about CSS.

## Author

- Frontend Mentor - [@cia2003](https://www.frontendmentor.io/profile/cia2003)
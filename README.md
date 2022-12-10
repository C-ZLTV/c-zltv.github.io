# Personal Website - Cristina Zlatov

This is my first project I build for the online Frontend Developer course by [Start2Impact](https://www.start2impact.it/).

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
- [Acknowledgments](#acknowledgments)

## Overview

### The challenge

Build a fully responsive personal website to showcase personal coding skills acquired during the CSS & HTML course. Most importantly Semantic HTML, Flexbox, Responsive Design & Images, Web Typography, Sass.

### Links

- URL: [Live Website URL](https://c-zltv.github.io/html-css-website/)

## My process

Started by writing the HTML for the project and using semantic tags to efficiently divide the website in sections: so we have a header with a navigation bar and a hero section, three sections inside the main content and a footer for contacts.

I proceeded by diving the Sass code in different files for intelligibility reasons: so we have a file for all the main Semanctic Elements (header, nav, main, footer, buttons), other utility filies (abstracts and reset) and finally a separate @media file.

The first Sass code was the reset which includes crucial reset elements such as: border-box box-sizing, responsive images base with 100% max-width and block display and zero margins for the body.

Everyting has been centered with a max() function for the width and a margin-inline set to auto.

The Navigation Bar is responsive with a regular Logo and Anchor Links template separated by space-between for Desktop and a on/off Hamburger Menu for Mobile, made interactive with JS. In the navigation file were included all the shared base styles for mobile and desktop versions while the separate mobile and desktop styles were included in two separate media queries for simplicity.

All the hero section text was made responsive with clamp() functions that provide mimimun, ideal and maximum sizes so there was no need for @media queries. The same approach was taken for the button with the addition of padding expressed in em unit instead of rem.

The first section, Vision and Story has 2 main blocks both with a paragraph and a responsive image that simply fall as follows on the mobile version but are made into row and reverse-row with flexbox for desktop.

The second section, Skills has a similar structure to the first one but instead of images the main focus are the buttons made responsive and fluid with flexbox and specifically setting flex-grow to 1 and activating wrap. In addition to this, all the eight buttons have a unique hover effect that displays all the colors used in the drawings.

The last section, Experiences is more simple, with only text and borders to divide the content. It mantaines the same look for both the mobile and the desktop version.

The final part of the website, the footer includes all the contact links. They are made accessible with a link integrated inside a button and an icon besides them, that esplicates what each button is for. On the mobile version the buttons simply fall in a colum as per default while on the desktop version they are in a row thanks to flexbox. The icon-button relationship is also governed by flexbox.

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow
- [Sass](https://sass-lang.com/) - CSS extension language

### What I learned

This project has been a learning moment for me for so many reasons and it pushed me to research and look into things bellow the surface.

Especially how every semantic tag or div can serve a very specfic but crucial purpose such as separate wrapper divs used for backgound-color, centering and flexbox:

```css
.snv,
.skills,
.exp,
.contacs {
  background-color: #323232ff;

  .container {
    margin-inline: auto;
    width: min(90%, 70.5rem);
  }
}

.story,
.vision {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

Or the importance of a thoughtful resent that saves a lot of time and headache in the long run:

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}

img {
  max-width: 100%;
  display: block;
}

input,
button,
textarea,
select {
  font: inherit;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
```

The navigation bar was definitely the most challenging part of the project but with some simple attributes and some JS everyting was made possible:

```html
<button class="mobile-nav-toggle" aria-expanded="false"></button>
<ul class="primary-navigation nav-flex" data-visible="false">
  ...
</ul>
```

```css
.primary-navigation {
  z-index: 1000;
  position: fixed;
  inset: 0 0 0 50%;

  transform: translateX(100%);
  transition: transform 0.3s ease-out;
}

.primary-navigation[data-visible="true"] {
  transform: translateX(0%);
}

.mobile-nav-toggle {
  z-index: 9999;
  position: fixed;
  top: 0.75rem;
  right: 1.5rem;

  background: url(../img/icon-hamburger.svg);
  background-repeat: no-repeat;
}

.mobile-nav-toggle[aria-expanded="true"] {
  background: url(../img/icon-close.svg);
  background-repeat: no-repeat;
}
```

Another important lesson was the clamp() function that made everyting so much easier:

```css
font-size: clamp(2rem, 4.5vw, 3.5rem);
```

### Continued development

I'm planning on continuing to develop the websit especially as I will start learning JS so it will be possibile to implemet some new and interesting features to make the website more fun.

### Useful resources

Beside the course I've taken with Start2Impact, I feel lucky to have found some great people on the Internet that really know their thing and are fanstic at explaining it. Some of these include:

- [Kevin Powell](https://www.youtube.com/@KevinPowell) - whose [21 days Responsive layout free course](https://courses.kevinpowell.co/view/courses/conquering-responsive-layouts) I followed while working on the project. It might as well be one of the best free Resource I've come accross.

- [CSS Reset by Andy Bell](https://piccalil.li/blog/a-modern-css-reset/) - intelligently written in 2019 still seems to be one the first and best things I've seen mentioned by experienced developers when talking about css reset.

- [SuperSimpleDev](https://www.youtube.com/@SuperSimpleDev) - whose youtube videos I watched regaring CSS and Git&Github. The Git&Github videos where probably the most in deth and complete beginner friendly explanations that I've come across and that actually made me understant important concepts.

## Author

- Website - [Personal Website URL](https://c-zltv.github.io/personal-website/)
- Twitter - [@czltv](https://twitter.com/czltv)

## Acknowledgments

Finally I'd like to thank Start2Impact for inspiring me to take on their course in the first place and making me feel comfortable while learning everything from 0.

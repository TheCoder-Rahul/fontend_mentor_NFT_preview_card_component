# Frontend Mentor - NFT preview card component solution

This is a solution to the [NFT preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![Design screenshot](https://github.com/TheCoder-Rahul/fontend_mentor_NFT_preview_card_component/blob/main/project_screenshot.png)


### Links

- 👉 [Solution URL](https://github.com/TheCoder-Rahul/fontend_mentor_NFT_preview_card_component.git)
- 👉 [Live Site URL](https://thecoder-rahul.github.io/fontend_mentor_NFT_preview_card_component/)

## My process

### Built with

- 👉 **Markup:** Semantic HTML5 for better accessibility and SEO.
- 👉 **Styling:** CSS3 with Custom Properties (variables) for a maintainable color scheme, font-properties, and different sizes.
- 👉 **Layout:** CSS Grid (Grid Template Areas) for the main layout and Flexbox for internal component alignment.
- 👉 **Workflow:** Mobile-first approach and Responsive Design using Media Queries.

### What I learned

In this challenge I learned how to handle data from a JSON file and include it in our HTML output.

Check my code snippets below:

```html
<article>
  <div class="img_wrapper">
    <img class="view_icon" src="./images/icon-view.svg" alt="View icon">
    <img class="nft_image" src="./images/image-equilibrium.jpg" alt="Equilibrium image">
  </div>
  <h1 class="nft_id"><a href="#" rel="noopener noreferrer">Equilibrium #3429</a></h1>
  <p class="nft_desc">Our Equilibrium collection promotes balance and calm.</p>
  <section class="nft_info">
    <p class="price">
      <img class="icon" src="./images/icon-ethereum.svg" alt="Ethereum icon">
      0.041 ETH
    </p>
    <p class="time_left">
      <img class="icon" src="./images/icon-clock.svg" alt="Clock icon">
      3 days left
    </p>
  </section>
  <hr>
  <div class="nft_creator">
    <img class="profile_img" src="./images/image-avatar.png" alt="Creator Profile Picture">
    <p>Creation of <a class="creator_name" href="#" rel="noopener noreferrer">Jules Wyvern</a></p>
  </div>
</article>
```
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
:root {
  --fw-light: 300;
  --fw-normal: 400;
  --fw-semibold: 600;
  --fs-body: 1rem;
  --clr-primary-500: 215, 51%, 70%;
  --clr-primary-400: 178, 100%, 50%;
  --clr-neutral-950: 217, 54%, 11%;
  --clr-neutral-900: 216, 50%, 16%;
  --clr-neutral-800: 215, 32%, 27%;
  --clr-neutral-100: 0, 0%, 100%;
  --font-family: 'Outfit', sans-serif;
}
body {
  height: 100vh;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
  font-family: var(--font-family);
  color: hsla(var(--clr-primary-500));
  background-color: hsla(var(--clr-neutral-950));
}
img {
  height: auto;
  max-width: 100%;
}
article {
  padding: 1.5rem;
  border-radius: 1rem;
  width: min(25rem, 90%);
  background-color: hsla(var(--clr-neutral-900));
  box-shadow: 0rem 1rem 1rem hsla(var(--clr-neutral-900), 0.5);
}
article .img_wrapper {
  width: 100%;
  display: flex;
  cursor: pointer;
  overflow: hidden;
  position: relative;
  align-items: center;
  border-radius: 0.5rem;
  margin-bottom: 1.5rem;
  justify-content: center;
}
article .img_wrapper::after {
  inset: 0;
  opacity: 0;
  content: '';
  position: absolute;
  -webkit-transition: opacity .3s ease-in-out;
  -moz-transition: opacity .3s ease-in-out;
  -ms-transition: opacity .3s ease-in-out;
  -o-transition: opacity .3s ease-in-out;
  transition: opacity .3s ease-in-out;
  background-color: hsla(var(--clr-primary-400), 0.5);
}
article .view_icon {
  opacity: 0;
  z-index: 1;
  position: absolute;
  -webkit-transition: opacity .3s ease-in-out;
  -moz-transition: opacity .3s ease-in-out;
  -ms-transition: opacity .3s ease-in-out;
  -o-transition: opacity .3s ease-in-out;
  transition: opacity .3s ease-in-out;
}
article .img_wrapper:hover::after, article .img_wrapper:hover .view_icon {
  opacity: 1;
}
article .nft_id {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  font-weight: var(--fw-semibold);
}
article .nft_id a {
  text-decoration: none;
  color: hsla(var(--clr-neutral-100));
  -webkit-transition: all 0.3s ease-in-out;
  -moz-transition: all 0.3s ease-in-out;
  -ms-transition: all 0.3s ease-in-out;
  -o-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}
article .nft_id a:hover {
  color: hsla(var(--clr-primary-400));
}
article .nft_desc {
  line-height: 1.5;
  margin-bottom: 1rem;
  font-size: var(--fs-body);
  font-weight: var(--fw-light);
  color: hsla(var(--clr-primary-500));
}
article .nft_info {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
article .nft_info .price, article .nft_info .time_left {
  display: flex;
  column-gap: 0.5rem;
  align-items: center;
  font-weight: var(--fw-normal);
}
article .nft_info .price {
  color: hsla(var(--clr-primary-400));
  font-weight: var(--fw-semibold);
}
hr {
  height: 1px;
  border: none;
  margin: 1rem 0;
  background-color: hsla(var(--clr-neutral-800));
}
.nft_creator {
  display: flex;
  align-items: center;
  column-gap: 0.75rem;
}
.nft_creator .profile_img {
  width: 2rem;
  border-radius: 50%;
  border: 2px solid hsla(var(--clr-neutral-100));
}
.nft_creator .creator_name {
  text-decoration: none;
  color: hsla(var(--clr-neutral-100));
  -webkit-transition: all 0.3s ease-in-out;
  -moz-transition: all 0.3s ease-in-out;
  -ms-transition: all 0.3s ease-in-out;
  -o-transition: all 0.3s ease-in-out;
  transition: all 0.3s ease-in-out;
}
.nft_creator .creator_name:hover {
  color: hsla(var(--clr-primary-400));
}
.attribution { font-size: 11px; text-align: center; position: absolute; bottom: 1rem; }
.attribution a { color: hsla(var(--clr-primary-500)); }
```

## Author

- 👉 GitHub - [TheCoder-Rahul](https://github.com/TheCoder-Rahul)
- 👉 Frontend Mentor - [@TheCoder-Rahul](https://www.frontendmentor.io/profile/TheCoder-Rahul)
- 👉 LinkedIn - [@Rahul Kumar](https://www.linkedin.com/in/rahul-the-developer/)
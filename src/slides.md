---
toc: false
sidebar: false
footer: false
title: Hello, simple slideshow
---

```js
let i = 0;
const slides = document.querySelectorAll(".slide");
function goto() {
  slides[i].scrollIntoView({behavior: "smooth"});
}
window.addEventListener("keydown", function(e) {
  switch (e.key) {
    case "ArrowDown":
      if (i < slides.length - 1) i += 1;
      e.preventDefault();
      goto();
      break;
    case "ArrowUp":
      if (i > 0) i -= 1;
      e.preventDefault();
      goto();
      break;
  }
})
```

<div class="slide">
    Hello slide 1
</div>

<div class="slide">
    Hello slide 2
</div>

<div class="slide">
    Hello slide 3
</div>


<style>
* {
    box-sizing: border-box;
}
#observablehq-center,
#observablehq-main {
    margin: 0;
}
html, body, main {
    width: 100%;
    height: 100%;
    overflow: hidden;
}
.slide {
    height: 100vh;
    font-family: sans-serif;
    padding: 3vw;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 5vw;
}
</style>

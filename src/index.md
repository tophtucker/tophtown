---
theme: alt
toc: false
---

<style>

.hero {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-family: var(--sans-serif);
  margin: 4rem 0 8rem;
  text-wrap: balance;
  text-align: center;
}

.hero h1 {
  margin: 2rem 0;
  max-width: none;
  font-size: 14vw;
  font-weight: 900;
  line-height: 1;
  background: linear-gradient(30deg, var(--theme-foreground-focus), currentColor);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero h2 {
  margin: 0;
  max-width: 34em;
  font-size: 20px;
  font-style: initial;
  font-weight: 500;
  line-height: 1.5;
  color: var(--theme-foreground-muted);
}

@media (min-width: 640px) {
  .hero h1 {
    font-size: 90px;
  }
}

</style>

<div class="hero">
  <h1 can-move id="welcome">Welcome to Tophtown</h1>
</div>

Flipper length: <input id="slider" type=range min=172 max=231 can-play>

```js
const x = Generators.input(document.querySelector("#slider"));
```

```js
const selection = view(Plot.plot({
  marks: [
    Plot.dot(penguins, {x: "body_mass_g", y: "culmen_length_mm", stroke: "species", filter: d => d.flipper_length_mm >= x, tip: true})
  ]
}));
```

```js
display(selection);
```

```js
const slider = document.querySelector("#slider");
slider.defaultData = { value: 172 };
slider.onMount = ({setData}) => {
  slider.addEventListener("input", (_e) => {
    setData({ value: slider.value });
  });
};
slider.updateElement = ({ element, data }) => {
  element.value = +data.value;
  element.dispatchEvent(new Event("input", { bubbles: true }));
};
```

```js
import { playhtml } from "https://unpkg.com/playhtml@latest";
playhtml.init();
```

<script src="https://cursor-party.spencerc99.partykit.dev/cursors.js"></script>
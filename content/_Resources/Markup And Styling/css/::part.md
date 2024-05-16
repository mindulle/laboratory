::part()
========

The `::part` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents any element within a
[shadow
tree](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)
that has a matching
[`part`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#part)
attribute.

[css]

```css
custom-element::part(foo) {
  /* Styles to apply to the `foo` part */
}
```

Syntax
------

[css]

```css
::part(<ident>+) {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<template id="tabbed-custom-element">
  <style>
    *,
    ::before,
    ::after {
      box-sizing: border-box;
      padding: 1rem;
    }
    :host {
      display: flex;
    }
  </style>
  <div part="tab active">Tab 1</div>
  <div part="tab">Tab 2</div>
  <div part="tab">Tab 3</div>
</template>

<tabbed-custom-element></tabbed-custom-element>
```

### CSS

[css]

```css
tabbed-custom-element::part(tab) {
  color: #0c0dcc;
  border-bottom: transparent solid 2px;
}

tabbed-custom-element::part(tab):hover {
  background-color: #0c0d19;
  color: #ffffff;
  border-color: #0c0d33;
}

tabbed-custom-element::part(tab):hover:active {
  background-color: #0c0d33;
  color: #ffffff;
}

tabbed-custom-element::part(tab):focus {
  box-shadow:
    0 0 0 1px #0a84ff inset,
    0 0 0 1px #0a84ff,
    0 0 0 4px rgba(10, 132, 255, 0.3);
}

tabbed-custom-element::part(active) {
  color: #0060df;
  border-color: #0a84ff !important;
}
```

### JavaScript

[js]

```js
let template = document.querySelector("#tabbed-custom-element");
globalThis.customElements.define(
  template.id,
  class extends HTMLElement {
    constructor() {
      super().attachShadow().append(template.content);
    }
  },
);
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Shadow Parts\
  [\# part]](https://drafts.csswg.org/css-shadow-parts/#part)

  -----------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`::part`

73

79

72

No

60

13.1

73

73

79

52

13.4

11.0

See also
--------

- The
    [`part`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#part)
    attribute - Used to define parts which can be selected by the
    `::part()` selector
- The
    [`exportparts`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#exportparts)
    attribute - Used to transitively export shadow parts from a nested
    shadow tree into a containing light tree.
- [CSS shadow parts](css_shadow_parts.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::part>

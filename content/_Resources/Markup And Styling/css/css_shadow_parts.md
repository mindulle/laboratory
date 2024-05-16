CSS shadow parts
================

The **CSS shadow parts** module defines the [`::part()`](::part)
pseudo-element that can be set on a [shadow
host](https://developer.mozilla.org/en-US/docs/Glossary/Shadow_tree).
Using this pseudo-element, you can enable shadow hosts to expose the
selected element in the shadow tree to the outside page for styling
purposes.

By default, elements in a shadow tree can be styled only within their
respective shadow roots. The CSS shadow parts module enables including a
[`part`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#part)
attribute on
[`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
descendants that make up the custom element, exposing the shadow tree
node to external styling via the `::part()` pseudo-element.

Reference
---------

### Selectors

- [`::part()`](::part)

### HTML attributes

- [`part`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#part)
- [`exportparts`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#exportparts)

### Definitions

- [Shadow
    tree](https://developer.mozilla.org/en-US/docs/Glossary/Shadow_tree)

Guides
------

[CSS pseudo-elements](pseudo-elements.md)

:   Alphabetical list of pseudo-elements defined by all the CSS
    specifications and WebVTT

[Web components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)

:   Overview of the different APIs that enable creating reusable custom
    elements or web components.

Related concepts
----------------

- HTML
    [`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
    element
- HTML
    [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot)
    element
- [`Element.part`](https://developer.mozilla.org/en-US/docs/Web/API/Element/part)
    property
- [`Element.shadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/shadowRoot)
    property
- [`Element.attachShadow()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow)
    method
- [`ShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot)
    interface
- [CSS scoping](css_scoping.md) module
  - [`:host`](:host)
  - [`:host()`](:host_function)
  - [`:host-context()`](:host-context)
  - [`::slotted`](::slotted)

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Shadow Parts\
  ](https://drafts.csswg.org/css-shadow-parts/)

  -----------------------------------------------------------------------

See also
--------

- [CSS pseudo elements](css_pseudo-elements.md) module
- [CSS selectors](css_selectors.md) module
- [Using shadow
    DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)
- [Templates: Styling outside of the current
    scope](https://web.dev/learn/html/template/#styling-outside-of-the-current-scope)
    on web.dev (2023)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_shadow_parts>

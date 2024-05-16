:host-context()
===============

The `:host-context()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) function selects the shadow host of the
[shadow
DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)
containing the CSS it is used inside (so you can select a custom element
from inside its shadow DOM) --- but only if the selector given as the
function\'s parameter matches the shadow host\'s ancestor(s) in the
place it sits inside the DOM hierarchy.

In other words, this allows a custom element, or anything within that
custom element\'s shadow DOM, to apply different styles based on its
position within the outer DOM or classes/attributes applied to ancestor
elements.

One typical use of this is with a descendant selector expression --- for
example `h1` --- to select only instances of the custom element that are
inside an `<h1>`. Another typical use would be to allow inner elements
to react to classes or attributes on any ancestor elements - for
example, applying a different text color when a `.dark-theme` class is
applied to `<body>`.

**Note:** This has no effect when used outside a shadow DOM.

Try it
------

[css]

```css
/* Selects a shadow root host, only if it is
   a descendant of the selector argument given */
:host-context(h1) {
  font-weight: bold;
}

/* Changes paragraph text color from black to white when
   a .dark-theme class is applied to the document body */
p {
  color: #000;
}

:host-context(body.dark-theme) p {
  color: #fff;
}
```

Syntax
------

[css]

```css
:host-context(<compound-selector>) {
  /* ... */
}
```

Examples
--------

### Selectively styling shadow hosts

The following snippets are taken from our [host-selectors
example](https://github.com/mdn/web-components-examples/tree/main/host-selectors)
([see it live
also](https://mdn.github.io/web-components-examples/host-selectors/)).

In this example we have a simple custom element --- `<context-span>` ---
that you can wrap around text:

[html]

```html
<h1>
  Host selectors <a href="#"><context-span>example</context-span></a>
</h1>
```

Inside the element\'s constructor, we create `style` and `span`
elements, fill the `span` with the content of the custom element, and
fill the `style` element with some CSS rules:

[js]

```js
const style = document.createElement("style");
const span = document.createElement("span");
span.textContent = this.textContent;

const shadowRoot = this.attachShadow();
shadowRoot.appendChild(style);
shadowRoot.appendChild(span);

style.textContent =
  "span:hover " +
  ":host-context(h1) " +
  ':host-context(h1):after ' +
  ":host(.footer) " +
  ":host ";
```

The `:host-context(h1)` and
`:host-context(h1):after` rules
style the instance of the `<context-span>` element (the shadow host in
this instance) inside the `<h1>`. We\'ve used it to make it clear that
the custom element shouldn\'t appear inside the `<h1>` in our design.

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Scoping Module Level 1\
  [\#
  host-selector]](https://drafts.csswg.org/css-scoping/#host-selector)

  ------------------------------------------------------------------------------

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

`:host-context`

54

79

No

No

41

No

54

54

No

41

No

6.0

See also
--------

- [Web
    components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)
- CSS [`:host`](:host) pseudo-class
- CSS [`:host()`](:host_function) pseudo-class
- CSS [`::slotted`](::slotted) pseudo-element
- HTML
    [`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
    element
- [CSS scoping](css_scoping.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:host-context>

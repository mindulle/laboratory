:host
=====

The `:host` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selects the shadow host of the [shadow
DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)
containing the CSS it is used inside --- in other words, this allows you
to select a custom element from inside its shadow DOM.

**Note:** This has no effect when used outside a shadow DOM.

Try it
------

[css]

```css
/* Selects a shadow root host */
:host {
  font-weight: bold;
}
```

Syntax
------

[css]

```css
:host {
  /* ... */
}
```

Examples
--------

### Styling the shadow host

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
  ":host-context(article, aside) " +
  ":host(.footer) " +
  ":host ";
```

The `:host` rule
styles all instances of the `<context-span>` element (the shadow host in
this instance) in the document.

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

`:host`

54

79

63

No

41

10

54

54

63

41

10

6.0

See also
--------

- [Web
    components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)
- [`:host()`](:host_function)
- [`:host-context()`](:host-context)
- [`::slotted`](::slotted)
- [CSS scoping](css_scoping.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:host>

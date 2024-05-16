:host()
=======

The `:host()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) function selects the shadow host of the
[shadow
DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)
containing the CSS it is used inside (so you can select a custom element
from inside its shadow DOM) --- but only if the selector given as the
function\'s parameter matches the shadow host.

The most obvious use of this is to put a class name only on certain
custom element instances, and then include the relevant class selector
as the function argument. You can\'t use this with a descendant selector
expression to select only instances of the custom element that are
inside a particular ancestor. That\'s the job of
[`:host-context()`](:host-context).

**Note:** This has no effect when used outside a shadow DOM.

Try it
------

[css]

```css
/* Selects a shadow root host, only if it is
   matched by the selector argument */
:host(.special-custom-element) {
  font-weight: bold;
}
```

Syntax
------

[css]

```css
:host(<compound-selector>) {
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
  ":host-context(article, aside) " +
  ":host(.footer) " +
  ":host ";
```

The `:host(.footer)` rule styles all instances of the
`<context-span>` element (the shadow host in this instance) in the
document that have the `footer` class set on them --- we\'ve used it to
give instances of the element inside the
[`<footer>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer)
a special color.

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

`:host_function`

54

79

63

No

41

10Certain CSS selectors do not work (:host \> .local-child) and styling
slotted content (::slotted) is buggy.

54

54

63

41

10Certain CSS selectors do not work (:host \> .local-child) and styling
slotted content (::slotted) is buggy.

6.0

See also
--------

- [Web
    components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)
- [`:host`](:host)
- [`:host-context()`](:host-context)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:host_function>

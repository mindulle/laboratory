:root
=====

The `:root` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches the root element of a tree
representing the document. In HTML, `:root` represents the
[`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
element and is identical to the selector `html`, except that its
[specificity](specificity.md) is higher.

[css]

```css
/* Selects the root element of the document:
   <html> in the case of HTML */
:root {
  background: yellow;
}
```

Syntax
------

[css]

```css
:root {
  /* ... */
}
```

Examples
--------

### Declaring global CSS variables

`:root` can be useful for declaring global [](using_css_custom_properties.md):

[css]

```css
:root {
  --main-color: hotpink;
  --pane-padding: 5px 42px;
}
```

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  root-pseudo]](https://drafts.csswg.org/selectors/#root-pseudo)

  ------------------------------------------------------------------------

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

`:root`

1

12

1

9

9.5

1

37

18

4

14

1

1.0

See also
--------

- [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
- [`Document.rootElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/rootElement)
- [`Node.getRootNode()`](https://developer.mozilla.org/en-US/docs/Web/API/Node/getRootNode)
- [`Element.shadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/shadowRoot)
- [`ShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:root>

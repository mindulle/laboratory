:-moz-first-node
================

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

The `:-moz-first-node`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) is a [Mozilla
extension](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions)
that represents any element that is the first child node of some other
element. It differs from [`:first-child`](:first-child) because it does
not match a first-child element with (non-whitespace) text before it.

**Note:** Any whitespace at the start of an element is ignored for the
determination of `:-moz-first-node`.

Syntax
------

[css]

```css
:-moz-first-node {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
span:-moz-first-node {
  background-color: lime;
}
```

### HTML

[html]

```html
<p>
  <span>This matches!</span>
  <span>This doesn't match.</span>
</p>

<p>
  Blahblah.
  <span>This doesn't match because it's preceded by text.</span>
</p>
```

### Result

Specifications
--------------

Not part of any standard.

See also
--------

- [`:-moz-last-node`](:-moz-last-node)
- [`:first-child`](:first-child)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-first-node>

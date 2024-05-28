:-moz-last-node
===============

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

The `:-moz-last-node`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) is a [Mozilla
extension](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions)
that represents any element that is the last child node of some other
element. It differs from [`:last-child`](:last-child) because it does
not match a last-child element with (non-whitespace) text after it.

**Note:** Any whitespace at the end of an element is ignored for the
determination of `:-moz-last-node`.

Syntax
------

[css]

```css
:-moz-last-node {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
span:-moz-last-node {
  background-color: lime;
}
```

### HTML

[html]

```html
<p>
  <span>This does not match.</span>
  <span>This matches!</span>
</p>

<p>
  <span>This doesn't match because it's followed by text.</span>
  Blahblah.
</p>
```

### Result

Specifications
--------------

Not part of any standard.

See also
--------

- [`:-moz-first-node`](:-moz-first-node)
- [`:last-child`](:last-child)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-last-node>

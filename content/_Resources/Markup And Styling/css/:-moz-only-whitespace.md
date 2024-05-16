:-moz-only-whitespace
=====================

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

**Note:** In [Selectors Level
4](https://drafts.csswg.org/selectors-4/#the-empty-pseudo), the
[`:empty`](:empty) selector was changed to act like
`:-moz-only-whitespace`, but no browser currently supports this yet.

The `:-moz-only-whitespace`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches elements that only contain text
nodes that only contain
[whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace).
(This includes elements with empty text nodes and elements with no child
nodes.)

Syntax
------

[css]

```css
:-moz-only-whitespace {
  /* ... */
}
```

Examples
--------

### Simple :-moz-only-whitespace example

#### HTML

[html]

```html
<div> </div>
```

#### CSS

[css]

```css
div {
  border: 4px solid red;
}

:-moz-only-whitespace {
  border-color: lime;
}
```

#### Result

Specifications
--------------

Briefly defined as `:blank` in [Selectors Level
4](https://drafts.csswg.org/selectors-4/#changes-2018-02), but then the
functionality was merged into [`:empty`](:empty) and [`:blank`](:blank)
redefined to mean empty
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input).

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

`:-moz-only-whitespace`

No

No

1

No

No

No

No

No

4

No

No

No

See also
--------

- [`:blank`](:blank) [Experimental]
- [`:empty`](:empty)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:-moz-only-whitespace>

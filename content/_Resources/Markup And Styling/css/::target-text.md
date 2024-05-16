::target-text
=============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `::target-text`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) represents the text that has been
scrolled to if the browser supports [text
fragments](https://developer.mozilla.org/en-US/docs/Web/Text_fragments).
It allows authors to choose how to highlight that section of text.

[css]

```css
::target-text {
  background-color: pink;
}
```

Syntax
------

[css]

```css
::target-text {
  /* ... */
}
```

Examples
--------

### Highlighting text fragments

[css]

```css
::target-text {
  background-color: rebeccapurple;
  color: white;
}
```

To see this CSS in action follow the link to [scroll-to-text
demo](https://mdn.github.io/css-examples/target-text/index.html#:~:text=From%20the%20foregoing%20remarks%20we%20may%20gather%20an%20idea%20of%20the%20importance).

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  selectordef-target-text]](https://drafts.csswg.org/css-pseudo/#selectordef-target-text)

  -------------------------------------------------------------------------------------------------

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

`::target-text`

89

89

No

No

75

No

89

89

No

63

No

15.0

See also
--------

- [Text
    fragments](https://developer.mozilla.org/en-US/docs/Web/Text_fragments)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::target-text>

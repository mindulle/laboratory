overflow-inline
===============

The `overflow-inline`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) can be used to test how the output
device handles content that overflows the initial [](containing_block.md) along the inline axis.

Syntax
------

The `overflow-inline` feature is specified as a keyword value chosen
from the list below.

[`none`](#none)

:   Content that overflows the inline axis is not displayed.

[`scroll`](#scroll)

:   Content that overflows the inline axis can be seen by scrolling to
    it.

Examples
--------

### HTML

[html]

```html
<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam ac turpis
  eleifend, fringilla velit ac, aliquam tellus. Vestibulum ante ipsum primis in
  faucibus orci luctus et ultrices posuere cubilia Curae; Nunc velit erat,
  tempus id rutrum sed, dapibus ut urna. Integer vehicula nibh a justo imperdiet
  rutrum. Nam faucibus pretium orci imperdiet sollicitudin. Nunc id facilisis
  dui. Proin elementum et massa et feugiat. Integer rutrum ullamcorper eleifend.
  Proin sit amet tincidunt risus. Sed nec augue congue eros accumsan tincidunt
  sed eget ex.
</p>
```

### CSS

[css]

```css
p {
  white-space: nowrap;
}

@media (overflow-inline: scroll) {
  p {
    color: red;
  }
}
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  mf-overflow-inline]](https://drafts.csswg.org/mediaqueries/#mf-overflow-inline)

  -----------------------------------------------------------------------------------------

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

`overflow-inline`

113

113

66

No

99

17

113

113

66

No

17

No

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/overflow-inline>

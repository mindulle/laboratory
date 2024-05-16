size-adjust
===========

The `size-adjust` CSS descriptor for the [`@font-face`](@font-face.md)
at-rule defines a multiplier for glyph outlines and metrics associated
with this font. This makes it easier to harmonize the designs of various
fonts when rendered at the same font size.

The `size-adjust` descriptor behaves in a similar fashion to the
[`font-size-adjust`](font-size-adjust.md) property. It calculates an
adjustment per font by matching ex heights.

Syntax
------

[css]

```css
size-adjust: 90%;
```

### Values

[`<percentage>`](#percentage)

:   A [`<percentage>`](percentage.md) value with an initial value of
    100%.

All metrics associated with this font are scaled by the given
percentage. This includes glyph advances, baseline tables, and overrides
provided by [`@font-face`](@font-face.md) descriptors.

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `100%`
  Percentages                           as specified
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```text
size-adjust = 
  <percentage [0,∞]>  
```

Examples
--------

### Overriding metrics of a fallback font

The `size-adjust` property can help when overriding the metrics of a
fallback font to better match those of a primary web font.

[css]

```css
@font-face {
  font-family: web-font;
  src: url("https://example.com/font.woff");
}

@font-face {
  font-family: local-font;
  src: local(Local Font);
  size-adjust: 90%;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Fonts Module Level 5\
  [\#
  size-adjust-desc]](https://drafts.csswg.org/css-fonts-5/#size-adjust-desc)

  ------------------------------------------------------------------------------------

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

`size-adjust`

92

92

92

No

78

17

92

92

92

No

17

16.0

See also
--------

- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md) descriptor
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md) descriptor
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md) descriptor
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md) descriptor
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md) descriptor
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md) descriptor
- [`src`](src.md) descriptor
- [`unicode-range`](unicode-range.md) descriptor
- [`font-size-adjust`](font-size-adjust.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/size-adjust>

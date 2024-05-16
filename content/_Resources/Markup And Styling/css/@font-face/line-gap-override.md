line-gap-override
=================

The `line-gap-override` CSS descriptor for the
[`@font-face`](@font-face.md) at-rule defines the line-gap metric for
the font. The line-gap metric is the font recommended line-gap or
external leading.

Syntax
------

[css]

```css
line-gap-override: normal;
line-gap-override: 90%;
```

### Values

[`normal`](#normal)

:   The default value. When used the metric value is obtained from the
    font file.

[`<percentage>`](#percentage)

:   A [`<percentage>`](percentage.md) value.

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `normal`
  Percentages                           as specified
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```text
line-gap-override = 
  [ normal | <percentage [0,∞]> ]  
```

Examples
--------

### Overriding metrics of a fallback font

The `line-gap-override` property can help when overriding the metrics of
a fallback font to better match those of a primary web font.

[css]

```css
@font-face {
  font-family: web-font;
  src: url("https://example.com/font.woff");
}

@font-face {
  font-family: local-font;
  src: local(Local Font);
  line-gap-override: 125%;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-metrics-override-desc]](https://drafts.csswg.org/css-fonts/#font-metrics-override-desc)

  ------------------------------------------------------------------------------------------------------

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

`line-gap-override`

87

87

89

No

73

No

87

87

89

62

No

14.0

See also
--------

- [`descent-override`](descent-override.md)
- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`line-gap-override`](line-gap-override.md)
- [`src`](src.md)
- [`size-adjust`](size-adjust.md)
- [`unicode-range descriptor`](unicode-range.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/line-gap-override>

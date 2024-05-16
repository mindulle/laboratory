color-contrast()
================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `color-contrast()` functional notation takes a
[`color`](color_value.md) value and compares it to a list of other
[`color`](color_value.md) values, selecting the one with the highest
contrast from the list.

Syntax
------

[css]

```css
color-contrast(wheat vs tan, sienna, #d2691e)
color-contrast(#008080 vs olive, var(--myColor), #d2691e)
```

### Values

Functional notation: `color-contrast(color vs color-list)`

[`color`](#color)

:   Any valid [`<color>`](color_value.md).

[`vs`](#vs)

:   A literal token as a component of the syntax.

[`color-list`](#color-list)

:   A comma-separated list of at least two color values to compare with
    the first value.

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Color Module Level 6\
  [\#
  colorcontrast]](https://drafts.csswg.org/css-color-6/#colorcontrast)

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

`color-contrast`

No

No

No

No

No

15

No

No

No

No

15

No

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-contrast>

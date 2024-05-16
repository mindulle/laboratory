hwb()
=====

The `hwb()` functional notation expresses an
[sRGB](https://developer.mozilla.org/en-US/docs/Glossary/RGB) color
according to its hue, whiteness, and blackness. An optional alpha
component represents the color\'s transparency.

Try it
------

Syntax
------

[css]

```css
hwb(194 0% 0%) /* #00c3ff */
hwb(194 0% 0% / .5) /* #00c3ff with 50% opacity */
```

### Values

Functional notation: `hwb(H W B[ / A])`

[`H`](#h)

:   A [`<number>`](number.md), an [`<angle>`](angle.md), or the keyword
    `none`, which represents the hue angle. More details on this type
    can be found on the [`<hue>`](hue.md) reference.

[`W`](#w), `B`

:   Each as a [`<percentage>`](percentage.md) or the keyword `none`,
    which represent whiteness and blackness, respectively. They specify
    the amount of white and black to mix in, from `0%` (no whiteness or
    blackness) to `100%` (full whiteness or blackness).

    If `W + B = 100%`, it defines some shade of gray. If `W + B > 100%`,
    `W` and `B` are effectively normalized as `W / (W + B)` and
    `B / (W + B)`, respectively.

[`A`](#a) [Optional]

:   An [`<alpha-value>`](alpha-value.md) or the keyword `none`, where
    the number `1` corresponds to `100%` (full opacity).

**Note:** This functional notation serializes to sRGB values, and the
values of the red, green, blue components may be rounded in
serialization.

**Note:** See [](color_value.md#missing_color_components) for the effect of
`none`.

### Formal syntax

```
<hwb()> = 
  hwb( [ <hue> | none ] [ <percentage> | none ] [ <percentage> | none ] [ / [ <alpha-value> | none ] ]? )  

<hue> = 
  <number>  |
  <angle>   

<alpha-value> = 
  <number>      |
  <percentage>  
```

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  the-hwb-notation]](https://drafts.csswg.org/css-color/#the-hwb-notation)

  ----------------------------------------------------------------------------------

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

`hwb`

101

101

96

No

87

15

101

101

96

70

15

19.0

See also
--------

- [`<color>`](color_value.md): For a list of all color notations

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hwb>

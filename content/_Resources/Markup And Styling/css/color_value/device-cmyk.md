device-cmyk()
=============

The `device-cmyk()` functional notation is used to express CMYK colors
in a device dependent way, specifying the cyan, magenta, yellow, and
black components.

This approach to color is useful when creating material to be output to
a particular printer, when the output for particular ink combinations is
known. CSS processors may attempt to approximate the color, however the
end result is likely to be different to the printed result.

Syntax
------

[css]

```css
device-cmyk(0 81% 81% 30%);
device-cmyk(0 81% 81% 30% / .5);
device-cmyk(0 81% 81% 30% / .5, rgb(178 34 34));
```

### Values

Functional notation: `device-cmyk(C M Y K[ / A][, color])`

[`C`](#c), `M`, `Y`, `K`

:   [`<number>`](number.md) or [`<percentage>`](percentage.md) values
    providing the cyan, magenta, yellow, and black components of CMYK
    color.

[`A`](#a) [Optional]

:   An [`<alpha-value>`](alpha-value.md), where the number `1`
    corresponds to `100%` (full opacity).

[`color`](#color) [Optional]

:   An optional fallback [`<color>`](color_value.md) to use if the user
    agent does not know how to translate the CMYK color to RGB.

### Formal syntax

```
<device-cmyk()> = 
  device-cmyk( <cmyk-component> [ / <alpha-value> ]? )  

<cmyk-component> = 
  <number>      |
  <percentage>  

<alpha-value> = 
  <number>      |
  <percentage>  
```

Specifications
--------------

**No specification found**

No specification data found for `css.types.color.device-cmyk`.\
[Check for problems with this page](#on-github) or contribute a missing
`spec_url` to
[mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).
Also make sure the specification is included in
[w3c/browser-specs](https://github.com/w3c/browser-specs).

Browser compatibility
---------------------

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/device-cmyk>

\<hex-color\>
=============

The `<hex-color>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) is a notation for describing the *hexadecimal color
syntax* of an
[sRGB](https://developer.mozilla.org/en-US/docs/Glossary/RGB) color
using its primary color components (red, green, blue) written as
hexadecimal numbers, as well as its transparency.

A `<hex-color>` value can be used everywhere where a
[`<color>`](color_value.md) can be used.

Syntax
------

```
#RGB        // The three-value syntax
#RGBA       // The four-value syntax
#RRGGBB     // The six-value syntax
#RRGGBBAA   // The eight-value syntax
```

### Value

[`R`](#r) or `RR`

:   The *red* component of the color, as a case-insensitive hexadecimal
    number between `0` and `ff` (255). If there is only one number, it
    is duplicated: `1` means `11`.

[`G`](#g) or `GG`

:   The *green* component of the color, as a case-insensitive
    hexadecimal number between `0` and `ff` (255). If there is only one
    number, it is duplicated: `c` means `cc`.

[`B`](#b) or `BB`

:   The *blue* component of the color, as a case-insensitive hexadecimal
    number between `0` and `ff` (255). If there is only one number, it
    is duplicated: `9` means `99`.

[`A`](#a) or `AA` [Optional]

:   The *alpha* component of the color, indicating its transparency, as
    a case-insensitive hexadecimal number between `0` and `ff` (255). If
    there is only one number, it is duplicated: `e` means `ee`. `0`, or
    `00`, represents a fully transparent color, and `f`, or `ff`, a
    fully opaque one.

**Note:** The syntax is case-insensitive: `#00ff00` is the same as
`#00FF00`.

Examples
--------

### Hexadecimal syntax for a fully opaque hot pink

#### HTML

[html]

```html
<span>
  #f09
  <div class="c1"></div>
</span>
<span>
  #F09
  <div class="c2"></div>
</span>
<span>
  #ff0099
  <div class="c3"></div>
</span>
<span>
  #FF0099
  <div class="c4"></div>
</span>
```

#### CSS

[css]

```css
div {
  width: 40px;
  height: 40px;
}
.c1 {
  background: #f09;
}
.c2 {
  background: #f09;
}
.c3 {
  background: #ff0099;
}
.c4 {
  background: #ff0099;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------

  [CSS Color Module Level 4\
  [\#
  hex-notation]](https://drafts.csswg.org/css-color/#hex-notation)

  --------------------------------------------------------------------------

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

`hex-color`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`alpha_hexadecimal_notation`

62

79

49

No

49

10

62

62

49

47

9.3

8.0

See also
--------

- [`<color>`](color_value.md): the color data type
- [`rgb()`](rgb.md): the function allowing to set the three
    components of the color, as well as its transparency, using decimal
    values

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/hex-color>

font-stretch
============

The `font-stretch`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property selects
a normal, condensed, or expanded face from a font.

Try it
------

Syntax
------

[css]

```css
/* <font-stretch-css3> keyword values */
font-stretch: normal;
font-stretch: ultra-condensed;
font-stretch: extra-condensed;
font-stretch: condensed;
font-stretch: semi-condensed;
font-stretch: semi-expanded;
font-stretch: expanded;
font-stretch: extra-expanded;
font-stretch: ultra-expanded;

/* Percentage values */
font-stretch: 50%;
font-stretch: 100%;
font-stretch: 200%;

/* Global values */
font-stretch: inherit;
font-stretch: initial;
font-stretch: revert;
font-stretch: revert-layer;
font-stretch: unset;
```

This property may be specified as a single `<font-stretch-css3>` keyword
value or a single [`<percentage>`](percentage.md) value.

### Values

[`normal`](#normal)

:   Specifies a normal font face.

[`semi-condensed`](#semi-condensed), `condensed`, `extra-condensed`, `ultra-condensed`

:   Specifies a more condensed font face than normal, with
    `ultra-condensed` as the most condensed.

[`semi-expanded`](#semi-expanded), `expanded`, `extra-expanded`, `ultra-expanded`

:   Specifies a more expanded font face than normal, with
    `ultra-expanded` as the most expanded.

[`<percentage>`](#percentage)

:   A [`<percentage>`](percentage.md) value between 50% and 200%
    (inclusive). Negative values are not allowed for this property.

### Keyword to numeric mapping

The table below shows the mapping between the `<font-stretch-css3>`
keyword values and numeric percentages:

  Keyword             Percentage
  ------------------- ------------
  `ultra-condensed`   50%
  `extra-condensed`   62.5%
  `condensed`         75%
  `semi-condensed`    87.5%
  `normal`            100%
  `semi-expanded`     112.5%
  `expanded`          125%
  `extra-expanded`    150%
  `ultra-expanded`    200%

Description
-----------

Some font families offer additional faces in which the characters are
narrower than the normal face (*condensed* faces) or wider than the
normal face (*expanded* faces).

You can use `font-stretch` to select a condensed or expanded face from
such fonts. If the font you are using does not offer condensed or
expanded faces, this property has no effect.

### Font face selection

The face selected for a given value of `font-stretch` depends on the
faces supported by the font in question. If the font does not provide a
face that exactly matches the given value, then values less than 100%
map to a narrower face, and values greater than or equal to 100% map to
a wider face.

The table below demonstrates the effect of supplying various different
percentage values of `font-stretch` on two different fonts:

- [Anek Malayalam](https://fonts.google.com/specimen/Anek+Malayalam)
    is a variable google font that supports widths from 75% to 125%.
    Values below and above this range select the closest matching font.
- [Inconsolata](https://fonts.google.com/specimen/Inconsolata) is a
    variable font that offers a continuous range of widths from 50% to
    200%.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     a [font stretch](_Resources/Markup%20And%20Styling/css/font-stretch.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-stretch = 
  normal              |
  <percentage [0,∞]>  |
  ultra-condensed     |
  extra-condensed     |
  condensed           |
  semi-condensed      |
  semi-expanded       |
  expanded            |
  extra-expanded      |
  ultra-expanded      
```

Examples
--------

### Setting font stretch percentages

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-stretch-prop]](https://drafts.csswg.org/css-fonts/#font-stretch-prop)

  ------------------------------------------------------------------------------------

**Note:** The `font-stretch` property was initially defined in CSS 2,
but dropped in CSS 2.1 due to the lack of browser implementation. It was
brought back in CSS 3.

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

`font-stretch`

60A `font-stretch` definition must be added to the `@font-face` before
this property will function.

12

9

9

47A `font-stretch` definition must be added to the `@font-face` before
this property will function.

11

60A `font-stretch` definition must be added to the `@font-face` before
this property will function.

60A `font-stretch` definition must be added to the `@font-face` before
this property will function.

9

44A `font-stretch` definition must be added to the `@font-face` before
this property will function.

11

8.0A `font-stretch` definition must be added to the `@font-face` before
this property will function.

`percentage`

62

18

61

No

49

11.1

62

62

61

46

11.3

8.0

See also
--------

- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [Fundamental text and font
    styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)
- [CSS fonts](css_fonts.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-stretch>

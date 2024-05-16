font-variant-numeric
====================

The `font-variant-numeric` CSS property controls the usage of alternate
glyphs for numbers, fractions, and ordinal markers.

Try it
------

Syntax
------

[css]

```css
font-variant-numeric: normal;
font-variant-numeric: ordinal;
font-variant-numeric: slashed-zero;
font-variant-numeric: lining-nums; /* <numeric-figure-values> */
font-variant-numeric: oldstyle-nums; /* <numeric-figure-values> */
font-variant-numeric: proportional-nums; /* <numeric-spacing-values> */
font-variant-numeric: tabular-nums; /* <numeric-spacing-values> */
font-variant-numeric: diagonal-fractions; /* <numeric-fraction-values> */
font-variant-numeric: stacked-fractions; /* <numeric-fraction-values> */
font-variant-numeric: oldstyle-nums stacked-fractions;

/* Global values */
font-variant-numeric: inherit;
font-variant-numeric: initial;
font-variant-numeric: revert;
font-variant-numeric: revert-layer;
font-variant-numeric: unset;
```

This property can take one of two forms:

- either the keyword value `normal`
- or one or more of the other values listed below, space-separated, in
    any order.

### Values

[`normal`](#normal)

:   This keyword leads to the deactivation of the use of such alternate
    glyphs.

[`ordinal`](#ordinal)

:   This keyword forces the use of special glyphs for the ordinal
    markers, like 1st, 2nd, 3rd, 4th in English or a 1a in Italian. It
    corresponds to the OpenType values `ordn`.

[`slashed-zero`](#slashed-zero)

:   This keyword forces the use of a 0 with a slash; this is useful when
    a clear distinction between O and 0 is needed. It corresponds to the
    OpenType values `zero`.

[*`<numeric-figure-values`\>*](#numeric-figure-values)

:   These values control the figures used for numbers. Two values are
    possible:

    -   `lining-nums` activating the set of figures where numbers are
        all lying on the baseline. It corresponds to the OpenType values
        `lnum`.
    -   `oldstyle-nums` activating the set of figures where some
        numbers, like 3, 4, 7, 9 have descenders. It corresponds to the
        OpenType values `onum`.

[*`<numeric-spacing-values>`*](#numeric-spacing-values)

:   These values controls the sizing of figures used for numbers. Two
    values are possible:

    -   `proportional-nums` activating the set of figures where numbers
        are not all of the same size. It corresponds to the OpenType
        values `pnum`.
    -   `tabular-nums` activating the set of figures where numbers are
        all of the same size, allowing them to be easily aligned like in
        tables. It corresponds to the OpenType values `tnum`.

[*`<numeric-fraction-values>`*](#numeric-fraction-values)

:   These values controls the glyphs used to display fractions. Two
    values are possible:

    -   `diagonal-fractions` activating the set of figures where the
        numerator and denominator are made smaller and separated by a
        slash. It corresponds to the OpenType values `frac`.
    -   `stacked-fractions` activating the set of figures where the
        numerator and denominator are made smaller, stacked and
        separated by a horizontal line. It corresponds to the OpenType
        values `afrc`.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-variant-numeric = 
  normal                                              |
  [ <numeric-figure-values> || <numeric-spacing-values> || <numeric-fraction-values> || ordinal || slashed-zero ]  

<numeric-figure-values> = 
  lining-nums    |
  oldstyle-nums  

<numeric-spacing-values> = 
  proportional-nums  |
  tabular-nums       

<numeric-fraction-values> = 
  diagonal-fractions  |
  stacked-fractions   
```

Examples
--------

### Setting ordinal numeric forms

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variant-numeric-prop]](https://drafts.csswg.org/css-fonts/#font-variant-numeric-prop)

  ----------------------------------------------------------------------------------------------------

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

`font-variant-numeric`

52

79

34

No

39

9.1

52

52

34

41

9.3

6.0

See also
--------

- [`font-variant`](font-variant.md)
- [`font-variant-alternates`](font-variant-alternates.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-position`](font-variant-position.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-numeric>

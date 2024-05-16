sepia()
=======

The `sepia()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) converts the input image to sepia, giving
it a warmer, more yellow/brown appearance. Its result is a
[`<filter-function>`](filter-function.md).

Try it
------

Syntax
------

[css]

```css
sepia(amount)
```

### Parameters

[`amount`](#amount)

:   The amount of the conversion, specified as a [`<number>`](number.md)
    or a [`<percentage>`](percentage.md). A value of `100%` is
    completely sepia, while a value of `0%` leaves the input unchanged.
    Values between `0%` and `100%` are linear multipliers on the effect.
    The initial value for
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    is `0`.

Examples
--------

### Examples of correct values for sepia()

[css]

```css
sepia(0)     /* No effect */
sepia(.65)   /* 65% sepia */
sepia(100%)  /* Completely sepia */
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-sepia]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-sepia)

  ----------------------------------------------------------------------------------------------

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

`sepia`

18

12

35

No

15

6

4.4

53

35

14

6

6.0

See also
--------

The other [`<filter-function>`](filter-function.md) functions available
to be used in values of the [`filter`](filter.md) and
[`backdrop-filter`](backdrop-filter.md) properties include:

- [`blur()`](blur.md)
- [`brightness()`](brightness.md)
- [`contrast()`](contrast.md)
- [`drop-shadow()`](drop-shadow.md)
- [`grayscale()`](grayscale.md)
- [`hue-rotate()`](hue-rotate.md)
- [`invert()`](invert.md)
- [`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)
- [`saturate()`](saturate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/sepia>

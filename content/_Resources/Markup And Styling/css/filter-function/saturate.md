saturate()
==========

The `saturate()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) super-saturates or desaturates the input
image. Its result is a [`<filter-function>`](filter-function.md).

Try it
------

Syntax
------

[css]

```css
saturate(amount)
```

### Parameters

[`amount`](#amount)

:   The amount of the conversion, specified as a [`<number>`](number.md)
    or a [`<percentage>`](percentage.md). A value under `100%`
    desaturates the image, while a value over `100%` super-saturates it.
    A value of `0%` is completely unsaturated, while a value of `100%`
    leaves the input unchanged. The initial value for
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    is `1`.

Examples
--------

### Examples of correct values for saturate()

[css]

```css
saturate(0)     /* Completely unsaturated */
saturate(.4)    /* 40% saturated */
saturate(100%)  /* No effect */
saturate(200%)  /* Double saturation */
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-saturate]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-saturate)

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

`saturate`

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
- [`sepia()`](sepia.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/saturate>

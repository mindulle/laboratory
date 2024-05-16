opacity()
=========

The `opacity()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) applies transparency to the samples in the
input image. Its result is a [`<filter-function>`](filter-function.md).

Try it
------

**Note:** This function is similar to the more established
[`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md) property. The difference is that with filters,
some browsers provide hardware acceleration for better performance.

Syntax
------

[css]

```css
opacity(amount)
```

### Parameters

[`amount`](#amount)

:   The amount of the conversion, specified as a [`<number>`](number.md)
    or a [`<percentage>`](percentage.md). A value of `0%` is completely
    transparent, while a value of `100%` leaves the input unchanged.
    Values between `0%` and `100%` are linear multipliers on the effect.
    The initial value for
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    is `1`.

Examples
--------

### Examples of correct values for opacity()

[css]

```css
opacity(0%)   /* Completely transparent */
opacity(50%)  /* 50% transparent */
opacity(1)    /* No effect */
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-opacity]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-opacity)

  --------------------------------------------------------------------------------------------------

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

`opacity`

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

- The other [`<filter-function>`](filter-function.md) functions
    available to be used in values of the [`filter`](filter.md) and
    [`backdrop-filter`](backdrop-filter.md) properties include:
  - [`blur()`](blur.md)
  - [`brightness()`](brightness.md)
  - [`contrast()`](contrast.md)
  - [`drop-shadow()`](drop-shadow.md)
  - [`grayscale()`](grayscale.md)
  - [`hue-rotate()`](hue-rotate.md)
  - [`invert()`](invert.md)
  - [`saturate()`](saturate.md)
  - [`sepia()`](sepia.md)
- The CSS [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/opacity>

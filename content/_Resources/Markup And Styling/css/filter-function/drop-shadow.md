drop-shadow()
=============

The `drop-shadow()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) applies a drop shadow effect to the input
image. Its result is a [`<filter-function>`](filter-function.md).

Try it
------

A drop shadow is effectively a blurred, offset version of the input
image\'s alpha mask, drawn in a specific color and composited below the
image.

**Note:** This function is somewhat similar to the
[`box-shadow`](box-shadow.md) property. The `box-shadow` property
creates a rectangular shadow behind an element\'s *entire box*, while
the `drop-shadow()` filter function creates a shadow that conforms to
the shape (alpha channel) of the *image itself*.

Syntax
------

[css]

```css
/* Two length values */
/* drop-shadow( <length> <length> ) */
drop-shadow(5px 5px)

/* Three length values */
/* drop-shadow( <length> <length> <length> ) */
drop-shadow(5px 5px 15px)

/* Two length values and a color */
/* drop-shadow( <length> <length> <color> ) */
drop-shadow(5px 5px red)

/* Three length values and a color */
/* drop-shadow( <length> <length> <length> <color> ) */
drop-shadow(5px 5px 15px red)

/* The order of color and length values can be changed */
/* drop-shadow( <color> <length> <length> <length> ) */
drop-shadow(#e23 0.5rem 0.5rem 1rem)
```

The `drop-shadow()` function accepts a parameter of type `<shadow>`
(defined in the [`box-shadow`](box-shadow.md) property), with the
exception that the `inset` keyword and `spread` parameters are not
allowed.

### Parameters

[`<color>`](#color) [Optional]

:   Specifies the color for the shadow. If not specified, the value of
    the [`color`](_Resources/Markup%20And%20Styling/css/color.md) property defined in the parent element is
    used.

[`<length>`](#length)

:   Specifies the offset length of the shadow. This parameter accepts
    two or three values. If two values are specified, they are
    interpreted as `<offset-x>` (horizontal offset) and `<offset-y>`
    (vertical offset) values. Negative `<offset-x>` value places the
    shadow to the left of the element. Negative `<offset-y>` value
    places the shadow above the element. If not specified, the value of
    `0` is used for the missing length. If a third value is specified,
    it is interpreted as `<standard-deviation>`, which is the value of
    the standard deviation to the [Gaussian
    blur](https://en.wikipedia.org/wiki/Gaussian_blur) function. A
    larger `<standard-deviation>` value creates a larger and more
    blurred shadow. Negative values for `<standard-deviation>` are not
    allowed.

Formal syntax
-------------

Error: could not find syntax for this item

Examples
--------

### Setting a drop shadow

[html]

```html
<div>drop-shadow(16px 16px)</div>
<div>drop-shadow(16px 16px red)</div>
<div>drop-shadow(red 1rem 1rem 10px)</div>
<div>drop-shadow(-16px -16px red)</div>
```

[css]

```css
div {
  display: inline-block;
  margin: 0 0.5rem 2rem 1rem;
  padding: 0.5rem;
  height: 100px;
  width: 190px;
  vertical-align: top;
  background-color: #222;

  color: lime;
}

div:nth-child(1) {
  filter: drop-shadow(16px 16px);
}

div:nth-child(2) {
  filter: drop-shadow(16px 16px red);
}

div:nth-child(3) {
  filter: drop-shadow(red 1rem 1rem 10px);
}

div:nth-child(4) {
  filter: drop-shadow(-16px -6px red);
}
```

In the absence of a `<color>` value in the `drop-shadow()` function in
the first box, the shadow uses the value of the `color` property from
the element (`lime`). The second and third shadows illustrate that the
length and color values can be specified in any order. The third shadow
shows the blurring effect when a third `<length>` value is specified.
The fourth shadow uses negative offsets which shifts shadow to the left
and top.

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-drop-shadow]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-drop-shadow)

  ----------------------------------------------------------------------------------------------------------

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

`drop-shadow`

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
- [`grayscale()`](grayscale.md)
- [`hue-rotate()`](hue-rotate.md)
- [`invert()`](invert.md)
- [`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)
- [`saturate()`](saturate.md)
- [`sepia()`](sepia.md)
- [`box-shadow`](box-shadow.md) property
- [`text-shadow`](text-shadow.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/drop-shadow>

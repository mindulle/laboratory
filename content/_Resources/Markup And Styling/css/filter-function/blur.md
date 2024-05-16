blur()
======

The `blur()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) applies a [Gaussian
blur](https://en.wikipedia.org/wiki/Gaussian_blur) to the input image.
Its result is a [`<filter-function>`](filter-function.md).

Try it
------

Syntax
------

The `blur()` function applies a Gaussian blur to the elements on which
it is applied.

[css]

```css
blur(radius)
```

### Parameters

[`radius`](#radius)

:   The radius of the blur, specified as a [`<length>`](length.md). It
    defines the value of the standard deviation to the Gaussian
    function, i.e., how many pixels on the screen blend into each other;
    thus, a larger value will create more blur. A value of `0` leaves
    the input unchanged. The initial value for
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    is `0`. Percentage values are invalid.

### Setting a blur with pixels and with rem

[css]

```css
blur(0)        /* No effect */
blur(8px)      /* Blur with 8px radius */
blur(1.17rem)  /* Blur with 1.17rem radius */
```

SVG filter
----------

The SVG
[`<feGaussianBlur>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feGaussianBlur)
filter element can also be used to blur content. The filter\'s
`stdDeviation` attribute accepts up to two values enabling creating more
complex blur values. To create an equivalent blur, we include one value
for `stdDeviation`. This SVG effect can then be referenced by ID:

[html]

```html
<svg role="none">
  <filter id="blur11">
    <feGaussianBlur stdDeviation="1.1" edgeMode="duplicate" />
  </filter>
</svg>
```

The following declarations produce the same effect:

[css]

```css
filter: blur(1.1px);
filter: url(#blur11); /* with embedded SVG */
filter: url(folder/fileName.svg#blurr11); /* external svg filter definition */
```

Examples
--------

This example shows three images: the image with a `blur()` filter
function applied, the image with the equivalent SVG blur function
applied, and the original images for comparison:

[css]

```css
.filter {
  filter: blur(3.5px);
}
```

[html]

```html
<svg role="img" aria-label="Flag">
  <filter id="blur">
    <feGaussianBlur stdDeviation="3.5" edgeMode="duplicate" />
  </filter>
  <image xlink:href="flag.jpg" filter="url(#blur)" />
</svg>
```

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-blur]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-blur)

  --------------------------------------------------------------------------------------------

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

`blur`

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

- [CSS filter effects](css_filter_effects.md) module
- The other [`<filter-function>`](filter-function.md) functions
    available to be used in values of the [`filter`](filter.md) and
    [`backdrop-filter`](backdrop-filter.md) properties include:
  - [`brightness()`](brightness.md)
  - [`contrast()`](contrast.md)
  - [`drop-shadow()`](drop-shadow.md)
  - [`grayscale()`](grayscale.md)
  - [`hue-rotate()`](hue-rotate.md)
  - [`invert()`](invert.md)
  - [`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)
  - [`saturate()`](saturate.md)
  - [`sepia()`](sepia.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/blur>

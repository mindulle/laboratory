contrast()
==========

The `contrast()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) adjusts the contrast of the input image.
Its result is a [`<filter-function>`](filter-function.md).

Try it
------

Syntax
------

[css]

```css
contrast(amount)
```

### Values

[`amount`](#amount)

:   The contrast of the result, specified as a [`<number>`](number.md)
    or a [`<percentage>`](percentage.md). A value under `100%` decreases
    the contrast, while a value over `100%` increases it. A value of `0`
    or `0%` will create an image that is completely gray, while a value
    of `1` or `100%` leaves the input unchanged. Negative values are not
    allowed. The initial value for
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    is `1`.

The following are pairs of equivalent values:

[css]

```css
contrast(0) /* Completely gray */
contrast(0%)

contrast(0.65) /* 65% contrast */
contrast(65%)

contrast(1)     /* No effect */
contrast(100%)

contrast(2)  /* Double contrast */
contrast(200%)
```

### Formal syntax

Error: could not find syntax for this item

Examples
--------

### With the backdrop-filter property

This example applies a `contrast()` filter via the
[`backdrop-filter`](backdrop-filter.md) CSS property to the paragraph
and monospaced text, color shifting to the area behind the `<p>` and
`<code>`.

[css]

```css
.container {
  background: url(image.jpg) no-repeat center / contain #339;
}
p {
  backdrop-filter: contrast(0.5);
}
code {
  backdrop-filter: contrast(0.15);
}
```

### With the filter property

This example applies a `contrast()` filter via the [`filter`](filter.md)
CSS property, changing contrast by shifting colors of the entire
element, including content, border, background, and shadows.

[css]

```css
p:first-of-type {
  filter: contrast(30%);
}
p:last-of-type {
  filter: contrast(300%);
}
```

### With url() and the SVG contrast filter

The SVG
[`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)
element is used to define custom filter effects that can then be
referenced by
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id).
The `<filter>`\'s
[`<feComponentTransfer>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feComponentTransfer)
primitive enables pixel-level color remapping. Given the following:

[svg]

```
  <filter id="contrast">
    <feComponentTransfer>
      <feFuncR type="linear" slope="2" intercept="-0.5"/>
      <feFuncG type="linear" slope="2" intercept="-0.5"/>
      <feFuncB type="linear" slope="2" intercept="-0.5"/>
    </feComponentTransfer>
  </filter>
```

These values produce the same results:

[css]

```css
filter: contrast(200%);
filter: url(#contrast); /* with embedded SVG */
filter: url(folder/fileName.svg#contrast); /* external svg filter definition */
```

This example shows three images: the image with a `contrast()` filter
function applied, the image with an equivalent `url()` filter applied,
and the original images for comparison:

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-contrast]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-contrast)

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

`contrast`

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
  - [`blur()`](blur.md)
  - [`brightness()`](brightness.md)
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
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/contrast>

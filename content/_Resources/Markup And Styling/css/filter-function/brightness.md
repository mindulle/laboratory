brightness()
============

The `brightness()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[`<filter-function>`](filter-function.md) applies a linear multiplier
value on an element or an input image, making the image appear brighter
or darker.

Try it
------

Syntax
------

[css]

```css
brightness(amount)
```

### Values

[`amount`](#amount)

:   Brightness specified as a [`<number>`](number.md) or a
    [`<percentage>`](percentage.md). A value less than `100%` darkens
    the input image or element, while a value over `100%` brightens it.
    A value of `0%` creates a completely black image or element, while a
    value of `100%` leaves the input unchanged. Other values between
    `0%` to `100%` have a linear multiplier effect. Values greater than
    `100%` are allowed, providing brighter results. The initial value
    for
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    is `1`. Negative values are not allowed. The default value, when
    nothing is specified, is `1`.

The following are pairs of equivalent values:

[css]

```css
brightness(0) /* Brightness is reduced to zero, so input turns black */
brightness(0%)

brightness(0.4) /* Brightness of input is reduced to 40%, so input is 60% darker */
brightness(40%)

brightness(1) /* Brightness of input is not changed */
brightness(100%)

brightness(2) /* Brightness of input is doubled */
brightness(200%)
```

### Formal syntax

Error: could not find syntax for this item

Examples
--------

### Applying brightness using the backdrop-filter property

This example shows how to apply the `brightness()` filter to a paragraph
via the [`backdrop-filter`](backdrop-filter.md) CSS property.

#### CSS

[css]

```css
.container {
  background: url(image.jpg) no-repeat right / contain #d4d5b2;
}
p {
  backdrop-filter: brightness(150%);
  text-shadow: 2px 2px #ffffff;
}
```

#### Result

In this example, the colors in the area behind the `<p>` element shift
linearly. If the `backdrop-filter` property was set to `brightness(0%)`,
the `<div>` area with the `<p>` element would have been black and hidden
the image behind. At `brightness(100%)`, the `<div>` area color would be
the same as the input `#d4d5b2`, and the image behind would be
completely transparent. With the brightness set to `150%` as in this
example, the colors in the image behind are getting hidden by the
brightness of the `<div>` element.\`

### Applying brightness using the filter property

In this example, a `brightness()` filter is applied to the entire
element, including content, border, and background image via the
[`filter`](filter.md) CSS property. The result shows three variations of
different brightness values.

[css]

```css
p:first-of-type {
  filter: brightness(50%);
}
p:last-of-type {
  filter: brightness(200%);
}
```

### Applying brightness using the url() SVG brightness filter

The SVG
[`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)
element is used to define custom filter effects that can then be
referenced by
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id).
The `<filter>` element\'s
[`<feComponentTransfer>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feComponentTransfer)
primitive enables pixel-level color remapping.

In this example, to create a filter that darkens the content on which it
is applied by 25% (i.e., 75% of the original brightness), the `slope`
attribute is set to `0.75`. We can then reference the filter by `id`.

Given the following:

[html]

```html
<svg role="none">
  <filter id="darken25" color-interpolation-filters="sRGB">
    <feComponentTransfer>
      <feFuncR type="linear" slope="0.75" />
      <feFuncG type="linear" slope="0.75" />
      <feFuncB type="linear" slope="0.75" />
    </feComponentTransfer>
  </filter>
</svg>
```

The following declarations produce similar effects:

[css]

```css
filter: brightness(75%);
filter: url(#darken25); /* with embedded SVG */
filter: url(folder/fileName.svg#darken25); /* external svg filter definition */
```

In the images below, the first one has a `brightness()` filter function
applied, the second one has a similar SVG brightness function applied,
and the third is the original image for comparison.

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-brightness]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-brightness)

  --------------------------------------------------------------------------------------------------------

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

`brightness`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/brightness>

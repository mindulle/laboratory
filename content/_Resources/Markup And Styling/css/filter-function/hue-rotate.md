hue-rotate()
============

The `hue-rotate()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) rotates the
[hue](https://en.wikipedia.org/wiki/Hue) of an element and its contents.
Its result is a [`<filter-function>`](filter-function.md).

Try it
------

Syntax
------

The `hue-rotate()` function applies a color rotation to the elements on
which it is applied.

[css]

```css
hue-rotate(angle)
```

### Values

[`angle`](#angle)

:   The relative change in hue of the input sample, specified as an
    [`<angle>`](angle.md). A value of `0deg` leaves the input unchanged.
    A positive hue rotation increases the hue value, while a negative
    rotation decreases the hue value. The initial value for
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    is `0`. There is no minimum or maximum value. The effect of values
    above `360deg` are, given `hue-rotate(Ndeg)`, evaluates to `N`
    modulo 360.

The `<angle>` CSS data type represents an angle value expressed in
degrees, gradians, radians, or turns. The following are equivalent:

[css]

```css
hue-rotate(-180deg)
hue-rotate(540deg)
hue-rotate(200grad)
hue-rotate(3.14159rad)
hue-rotate(0.5turn)
```

### Formal syntax

Error: could not find syntax for this item

Examples
--------

### With the backdrop-filter property

This example applies a `hue-rotate()` filter via the `backdrop-filter`
CSS property to the paragraph, color shifting to the area behind the
`<p>`.

[css]

```css
.container {
  background: url(image.jpg) no-repeat left / contain #011296;
}
p {
  backdrop-filter: hue-rotate(240deg);
  text-shadow: 2px 2px #011296;
}
```

### With the filter property

This example applies a `hue-rotate()` filter via the `filter` CSS
property adding the color shift to the entire element, including
content, border, and background image.

[css]

```css
p {
  filter: hue-rotate(-60deg);
  text-shadow: 2px 2px blue;
  background-color: magenta;
  color: goldenrod;
  border: 1em solid rebeccapurple;
  box-shadow:
    inset -5px -5px red,
    5px 5px yellow;
}
```

### With url() and the SVG hue-rotate filter

The SVG
[`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)
element is used to define custom filter effects that can then be
referenced by
[`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#id).
The `<filter>`\'s
[`<feColorMatrix>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feColorMatrix)
primitive `hueRotate` type provides the same effect. Given the
following:

[svg]

```
<filter id="filterID">
  <feColorMatrix type="hueRotate" values="90" />
</filter>
```

These values produce the same results:

[css]

```css
filter: hue-rotate(90deg); /* 90deg rotation */
filter: url(#filterID); /* with embedded SVG */
filter: url(folder/fileName.svg#filterID); /* external svg filter definition */
```

This example shows three images: the image with a `hue-rotate()` filter
function applied, the image with an equivalent `url()` filter applied,
and the original images for comparison:

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  funcdef-filter-hue-rotate]](https://drafts.fxtf.org/filter-effects/#funcdef-filter-hue-rotate)

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

`hue-rotate`

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
  - [`contrast()`](contrast.md)
  - [`drop-shadow()`](drop-shadow.md)
  - [`grayscale()`](grayscale.md)
  - [`invert()`](invert.md)
  - [`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)
  - [`saturate()`](saturate.md)
  - [`sepia()`](sepia.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/hue-rotate>

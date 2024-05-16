shape-image-threshold
=====================

The `shape-image-threshold`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the alpha channel threshold used to extract the shape using an image as
the value for [`shape-outside`](shape-outside.md).

Try it
------

Any pixels whose alpha component\'s value is greater than the threshold
are considered to be part of the shape for the purposes of determining
its boundaries. For example, a value of `0.5` means that the shape will
enclose all the pixels that are more than 50% opaque.

Syntax
------

[css]

```css
/* <number> value */
shape-image-threshold: 0.7;

/* Global values */
shape-image-threshold: inherit;
shape-image-threshold: initial;
shape-image-threshold: revert;
shape-image-threshold: revert-layer;
shape-image-threshold: unset;
```

### Values

[`<alpha-value>`](alpha-value.md)

:   Sets the threshold used for extracting a shape from an image. The
    shape is defined by the pixels whose alpha value is greater than the
    threshold. Values outside the range 0.0 (fully transparent) to 1.0
    (fully opaque) are clamped to this range.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0.0`
  Applies to                         floats
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   The same as the specified value after clipping the [`<number>`](number.md) to the range \[0.0, 1.0\].
  Animation type                     a [number](number.md#interpolation)
  ---------------------------------- ----------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
shape-image-threshold = 
  <alpha-value>  

<alpha-value> = 
  <number>      |
  <percentage>  
```

Examples
--------

### Aligning text to a gradient

This example creates a
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
block with a gradient background image. The gradient is established as a
CSS shape using `shape-outside`, so that pixels within the gradient
which are at least 20% opaque (that is, those pixels with an alpha
component greater than 0.2) are considered part of the shape.

#### HTML

[html]

```html
<div id="gradient-shape"></div>

<p>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vel at commodi
  voluptates enim, distinctio officia. Saepe optio accusamus doloribus sint
  facilis itaque ab nulla, dolor molestiae assumenda cum sit placeat adipisci,
  libero quae nihil porro debitis laboriosam inventore animi impedit nostrum
  nesciunt quisquam expedita! Dolores consectetur iure atque a mollitia dicta
  repudiandae illum exercitationem aliquam repellendus ipsum porro modi, id nemo
  eligendi, architecto ratione quibusdam iusto nisi soluta? Totam inventore ea
  eum sed velit et eligendi suscipit accusamus iusto dolore, at provident eius
  alias maxime pariatur non deleniti ipsum sequi rem eveniet laboriosam magni
  expedita?
</p>
```

#### CSS

[css]

```css
#gradient-shape {
  width: 150px;
  height: 150px;
  float: left;
  background-image: linear-gradient(30deg, black, transparent 80%, transparent);
  shape-outside: linear-gradient(30deg, black, transparent 80%, transparent);
  shape-image-threshold: 0.2;
}
```

The shape is established here using
[`background-image`](background-image.md) with a linear gradient rather
than an image file. The same gradient is also used as the image from
which the shape is derived for establishing the float area, using the
[`shape-outside`](shape-outside.md) property.

The 20% opacity threshold for treating gradient pixels as part of the
shape is then established using `shape-image-threshold` with a value of
`0.2`.

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  shape-image-threshold-property]](https://drafts.csswg.org/css-shapes/#shape-image-threshold-property)

  ---------------------------------------------------------------------------------------------------------------

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

`shape-image-threshold`

37

79

62

No

24

10.1

37

37

62

24

10.3

3.0

`percentages`

78

79

70

No

65

No

78

78

79

56

No

12.0

See also
--------

- [CSS Shapes](css_shapes.md)
- [Overview of CSS Shapes](overview_of_shapes.md)
- [`<basic-shape>`](basic-shape.md)
- [`shape-outside`](shape-outside.md)
- [`shape-margin`](shape-margin.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/shape-image-threshold>

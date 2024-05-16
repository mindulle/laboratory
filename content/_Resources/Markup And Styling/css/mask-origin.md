mask-origin
===========

The `mask-origin`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the origin of a mask.

For elements rendered as a single box, this property specifies the mask
positioning area. In other words, this property specifies the origin
position of an image specified by the [`mask-image`](mask-image.md) CSS
property. For elements rendered as multiple boxes, such as inline boxes
on several lines or boxes on several pages, it specifies which boxes
[`box-decoration-break`](box-decoration-break.md) operates upon to
determine the mask positioning area.

Syntax
------

[css]

```css
/* Keyword values */
mask-origin: content-box;
mask-origin: padding-box;
mask-origin: border-box;
mask-origin: fill-box;
mask-origin: stroke-box;
mask-origin: view-box;

/* Multiple values */
mask-origin: padding-box, content-box;
mask-origin: view-box, fill-box, border-box;

/* Non-standard keyword values */
-webkit-mask-origin: content;
-webkit-mask-origin: padding;
-webkit-mask-origin: border;

/* Global values */
mask-origin: inherit;
mask-origin: initial;
mask-origin: revert;
mask-origin: revert-layer;
mask-origin: unset;
```

One or more of the keyword values listed below, separated by commas.

### Values

[`content-box`](#content-box)

:   The position is relative to the content box.

[`padding-box`](#padding-box)

:   The position is relative to the padding box. For single boxes `0 0`
    is the upper left corner of the padding edge, `100% 100%` is the
    lower right corner.

[`border-box`](#border-box)

:   The position is relative to the border box.

[`fill-box`](#fill-box) [Experimental]

:   The position is relative to the object bounding box.

[`stroke-box`](#stroke-box) [Experimental]

:   The position is relative to the stroke bounding box.

[`view-box`](#view-box) [Experimental]

:   Uses the nearest SVG viewport as reference box. If a `viewBox`
    attribute is specified for the element creating the SVG viewport,
    the reference box is positioned at the origin of the coordinate
    system established by the `viewBox` attribute and the dimension of
    the reference box is set to the width and height values of the
    `viewBox` attribute.

[`content`](#content) [Non-standard]

:   Same as `content-box`.

[`padding`](#padding) [Non-standard]

:   Same as `padding-box`.

[`border`](#border) [Non-standard]

:   Same as `border-box`.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `border-box`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-origin = 
  <geometry-box>#  

<geometry-box> = 
  <shape-box>  |
  fill-box     |
  stroke-box   |
  view-box     

<shape-box> = 
  <box>       |
  margin-box  

<box> = 
  border-box   |
  padding-box  |
  content-box  
```

Examples
--------

### Setting mask origin to border-box

Try some of the other possible values by updating the CSS in the box
below.

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-origin]](https://drafts.fxtf.org/css-masking/#the-mask-origin)

  ---------------------------------------------------------------------------------

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

`mask-origin`

1

79

53

No

15

15.44

2

18

53

14

15.43.2

1.0

`fill-box`

No

No

53

No

No

No

No

No

53

No

No

No

`non_standard_values`

1

79

No

No

15

15.44

2

18

No

14

15.43.2

1.0

`stroke-box`

No

No

53

No

No

No

No

No

53

No

No

No

`view-box`

No

No

53

No

No

No

No

No

53

No

No

No

See also
--------

- [Clipping and Masking in
    CSS](https://css-tricks.com/clipping-masking-css/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-origin>

mask-clip
=========

The `mask-clip` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property determines the area which is affected by a mask. The painted
content of an element must be restricted to this area.

Syntax
------

[css]

```css
/* <geometry-box> values */
mask-clip: content-box;
mask-clip: padding-box;
mask-clip: border-box;
mask-clip: fill-box;
mask-clip: stroke-box;
mask-clip: view-box;

/* Keyword values */
mask-clip: no-clip;

/* Non-standard keyword values */
-webkit-mask-clip: border;
-webkit-mask-clip: padding;
-webkit-mask-clip: content;
-webkit-mask-clip: text;

/* Multiple values */
mask-clip: padding-box, no-clip;
mask-clip: view-box, fill-box, border-box;

/* Global values */
mask-clip: inherit;
mask-clip: initial;
mask-clip: revert;
mask-clip: revert-layer;
mask-clip: unset;
```

One or more of the keyword values listed below, separated by commas.

### Values

[`content-box`](#content-box)

:   The painted content is clipped to the content box.

[`padding-box`](#padding-box)

:   The painted content is clipped to the padding box.

[`border-box`](#border-box)

:   The painted content is clipped to the border box.

[`fill-box`](#fill-box)

:   The painted content is clipped to the object bounding box.

[`stroke-box`](#stroke-box)

:   The painted content is clipped to the stroke bounding box.

[`view-box`](#view-box)

:   Uses the nearest SVG viewport as reference box. If a
    [`viewBox`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/viewBox)
    attribute is specified for the element creating the SVG viewport,
    the reference box is positioned at the origin of the coordinate
    system established by the `viewBox` attribute and the dimension of
    the reference box is set to the width and height values of the
    `viewBox` attribute.

[`no-clip`](#no-clip)

:   The painted content is not clipped.

[`border`](#border) [Non-standard]

:   This keyword behaves the same as `border-box`.

[`padding`](#padding) [Non-standard]

:   This keyword behaves the same as `padding-box`.

[`content`](#content) [Non-standard]

:   This keyword behaves the same as `content-box`.

[`text`](#text) [Non-standard]

:   This keyword clips the mask image to the text of the element.

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
mask-clip = 
  [ <geometry-box> | no-clip ]#  

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

### Clipping a mask to the border box

Change the `mask-clip` value to any of the allowed values detailed
above. If viewing the example in a Chromium-based browser change the
value of `-webkit-mask-clip`.

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-clip]](https://drafts.fxtf.org/css-masking/#the-mask-clip)

  -----------------------------------------------------------------------------

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

`mask-clip`

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

`border`

1

79

No

No

15

4

2

18

No

14

3.2

1.0

`content`

1

79

No

No

15

4

2

18

No

14

3.2

1.0

`padding`

1

79

No

No

15

4

2

18

No

14

3.2

1.0

`text`

1

79

No

No

15

4

2

18

No

14

3.2

1.0

See also
--------

- [Clipping and Masking in
    CSS](https://css-tricks.com/clipping-masking-css/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-clip>

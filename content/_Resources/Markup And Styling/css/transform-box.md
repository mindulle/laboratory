transform-box
=============

The `transform-box` CSS property defines the layout box to which the
[`transform`](transform.md), individual transform properties
[`translate`](_Resources/Markup%20And%20Styling/css/translate.md),[`scale`](_Resources/Markup%20And%20Styling/css/scale.md), and [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md), and
[`transform-origin`](transform-origin.md) properties relate.

Syntax
------

[css]

```css
/* Keyword values */
transform-box: content-box;
transform-box: border-box;
transform-box: fill-box;
transform-box: stroke-box;
transform-box: view-box;

/* Global values */
transform-box: inherit;
transform-box: initial;
transform-box: revert;
transform-box: revert-layer;
transform-box: unset;
```

The `transform-box` property is specified as one of the keyword values
listed below.

### Values

[`content-box`](#content-box)

:   The content box is used as the reference box. The reference box of a
    [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
    is the border box of its [table wrapper
    box](https://developer.mozilla.org/en-US/docs/Glossary/Table_Wrapper_Box),
    not its table box.

[`border-box`](#border-box)

:   The border box is used as the reference box. The reference box of a
    [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
    is the border box of its [table wrapper
    box](https://developer.mozilla.org/en-US/docs/Glossary/Table_Wrapper_Box),
    not its table box.

[`fill-box`](#fill-box)

:   The object bounding box is used as the reference box. For elements
    with associated CSS layout box, acts as `content-box`.

[`stroke-box`](#stroke-box)

:   The stroke bounding box is used as the reference box. For elements
    with associated CSS layout box, acts as `border-box`.

[`view-box`](#view-box)

:   The nearest
    [SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG)
    viewport is used as the reference box. If a `viewBox` attribute is
    specified for the SVG viewport creating element, the reference box
    is positioned at the origin of the coordinate system established by
    the `viewBox` attribute, and the dimension of the reference box is
    set to the width and height values of the `viewBox` attribute. For
    elements with associated CSS layout box, acts as `border-box`.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `view-box`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------

Formal syntax
-------------

```
transform-box = 
  content-box  |
  border-box   |
  fill-box     |
  stroke-box   |
  view-box     
```

Examples
--------

### SVG transform-origin scoping

In this example we have an SVG:

[html]

```html
<svg id="svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 50 50">
  <g>
    <circle id="center" fill="red" r="1" transform="translate(25 25)" />
    <circle id="boxcenter" fill="blue" r=".5" transform="translate(15 15)" />
    <rect
      id="box"
      x="10"
      y="10"
      width="10"
      height="10"
      rx="1"
      ry="1"
      stroke="black"
      fill="none" />
  </g>
</svg>
```

In the CSS we have an animation that uses a transform to rotate the
rectangle infinitely. `transform-box: fill-box` is used to make the
`transform-origin` the center of the bounding box, so the rectangle
spins in place. Without it, the transform origin is the center of the
SVG canvas, and so you get a very different effect.

[css]

```css
svg {
  width: 80vh;
  border: 1px solid #d9d9d9;
  position: absolute;
  margin: auto;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
}

#box {
  transform-origin: 50% 50%; /* anything other than `0 0` to see the effect */
  transform-box: fill-box;
  animation: rotateBox 3s linear infinite;
}

@keyframes rotateBox {
  to {
    transform: rotate(360deg);
  }
}
```

Full credit for this example goes to [Pogany](https://codepen.io/giaco);
see [this codepen](https://codepen.io/giaco/pen/OwowJQ) for a live
version.

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  transform-box]](https://drafts.csswg.org/css-transforms/#transform-box)

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

`transform-box`

64

79

55

No

51

11

64

64

55

47

11

9.0

`border-box`

118

No

≤72

No

104

13.1

118

118

79

No

13.4

No

`content-box`

118

No

preview

No

104

13.1

118

118

No

No

13.4

No

`stroke-box`

118

No

preview

No

104

13.1

118

118

No

No

13.4

No

See also
--------

- [Using CSS transforms](using_css_transforms.md)
- [`transform`](transform.md), [`transform-origin`](transform-origin.md)
- Individual transform properties:
  - [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
  - [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
  - [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-box>

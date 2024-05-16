offset-rotate
=============

The `offset-rotate` CSS property defines the orientation/direction of
the element as it is positioned along the [`offset-path`](offset-path.md).

Try it
------

**Note:** Early versions of the spec called this property
`motion-rotation`.

Syntax
------

[css]

```css
/* Follow the path direction, with optional additional angle */
offset-rotate: auto;
offset-rotate: auto 45deg;

/* Follow the path direction but facing the opposite direction of `auto` */
offset-rotate: reverse;

/* Keep a constant rotation regardless the position on the path */
offset-rotate: 90deg;
offset-rotate: 0.5turn;

/* Global values */
offset-rotate: inherit;
offset-rotate: initial;
offset-rotate: revert;
offset-rotate: revert-layer;
offset-rotate: unset;
```

[`auto`](#auto)

:   The element is rotated by the angle of the direction of the
    [`offset-path`](offset-path.md), relative to the positive x-axis. This
    is the default value.

`<angle>`

:   The element has a constant clockwise rotation transformation applied
    to it by the specified rotation angle.

[`auto <angle>`](#auto_angle)

:   If `auto` is followed by an [`<angle>`](angle.md), the computed value
    of the angle is added to the computed value of `auto`.

[`reverse`](#reverse)

:   The element is rotated similar to `auto`, except it faces the
    opposite direction. It is the same as specifying a value of
    `auto 180deg`.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     as \<angle\>, \<basic-shape\> or \<path()\>
  ---------------------------------- ---------------------------------------------

Formal syntax
-------------

```
offset-rotate = 
  [ auto | reverse ]  ||
  <angle>             
```

Examples
--------

### Setting element orientation along its offset path

#### HTML

[html]

```html
<div></div>
<div></div>
<div></div>
```

#### CSS

[css]

```css
div {
  width: 40px;
  height: 40px;
  background: #2bc4a2;
  margin: 20px;
  clip-path: polygon(0% 0%, 70% 0%, 100% 50%, 70% 100%, 0% 100%, 30% 50%);
  animation: move 5000ms infinite alternate ease-in-out;

  offset-path: path("M20,20 C20,50 180,-10 180,20");
}
div:nth-child(1) {
  offset-rotate: auto;
}
div:nth-child(2) {
  offset-rotate: auto 90deg;
}
div:nth-child(3) {
  offset-rotate: 30deg;
}

@keyframes move {
  100% {
    offset-distance: 100%;
  }
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [Motion Path Module Level 1\
  [\#
  offset-rotate-property]](https://drafts.fxtf.org/motion/#offset-rotate-property)

  ------------------------------------------------------------------------------------------

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

`offset-rotate`

565546

797979

72

No

434233

16

565546

565546

79

434233

16

6.06.05.0

See also
--------

- [`offset`](offset.md)
- [`offset-anchor`](offset-anchor.md)
- [`offset-distance`](offset-distance.md)
- [`offset-path`](offset-path.md)
- [`offset-position`](offset-position.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/offset-rotate>

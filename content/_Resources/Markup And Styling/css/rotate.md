rotate
======

The `rotate` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property allows you to specify rotation transforms individually and
independently of the [`transform`](transform.md) property. This maps better
to typical user interface usage, and saves having to remember the exact
order of transform functions to specify in the `transform` property.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
rotate: none;

/* Angle value */
rotate: 90deg;
rotate: 0.25turn;
rotate: 1.57rad;

/* x, y, or z axis name plus angle */
rotate: x 90deg;
rotate: y 0.25turn;
rotate: z 1.57rad;

/* Vector plus angle value */
rotate: 1 1 1 90deg;

/* Global values */
rotate: inherit;
rotate: initial;
rotate: revert;
rotate: revert-layer;
rotate: unset;
```

### Values

[angle value](#angle_value)

:   An [`<angle>`](angle.md) specifying the angle to rotate the affected
    element through, around the Z axis. Equivalent to a `rotate()` (2D
    rotation) function.

[x, y, or z axis name plus angle value](#x_y_or_z_axis_name_plus_angle_value)

:   The name of the axis you want to rotate the affected element around
    (`"x"`, \"`y`\", or \"`z"`), plus an [`<angle>`](angle.md) specifying
    the angle to rotate the element through. Equivalent to a
    `rotateX()`/`rotateY()`/`rotateZ()` (3D rotation) function.

[vector plus angle value](#vector_plus_angle_value)

:   Three [`<number>`](number.md)s representing an origin-centered vector
    that defines a line around which you want to rotate the element,
    plus an [`<angle>`](angle.md) specifying the angle to rotate the
    element through. Equivalent to a `rotate3d()` (3D rotation)
    function.

[`none`](#none)

:   Specifies that no rotation should be applied.

Formal definition
-----------------

  ------------------------------------------------------------------------------------------ ------------------------
  [Initial value](initial_value.md)                                                             `none`
  Applies to                                                                                 transformable elements
  [Inherited](inheritance.md)                                                                   no
  [Computed value](computed_value.md)                                                           as specified
  Animation type                                                                             a transform
  Creates [stacking context](stacking_context.md)   yes
  ------------------------------------------------------------------------------------------ ------------------------

Formal syntax
-------------

```
rotate = 
  none                                    |
  <angle>                                 |
  [ x | y | z | <number> ] && <angle>  
```

Examples
--------

### Rotating an element on hover

The following example shows how to use the `rotate` property to rotate
an element along various axes on hover. The first box rotates 90 degrees
on the Z axis hover, the second rotates 180 degrees on the Y axis on
hover, and the third rotates 360 degrees on hover around a vector
defined by coordinates.

#### HTML

[html]

```html
<div class="box" id="box1">rotate Z</div>
<div class="box" id="box2">rotate Y</div>
<div class="box" id="box3">vector & angle</div>
```

#### CSS

[css]

```css
.box {
  display: inline-block;
  margin: 1em;
  min-width: 6.5em;
  line-height: 6.5em;
  text-align: center;
  transition: 1s ease-in-out;
  border: 0.25em dotted;
}

#box1:hover {
  rotate: 90deg;
}

#box2:hover {
  rotate: y 180deg;
}

#box3:hover {
  rotate: 1 2 1 360deg;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  individual-transforms]](https://drafts.csswg.org/css-transforms-2/#individual-transforms)

  ---------------------------------------------------------------------------------------------------

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

`rotate`

104

104

72

No

90

14.1

104

104

79

71

14.5

20.0

`x_y_z_angle`

104

104

72

No

90

14.1

104

104

79

71

14.5

20.0

See also
--------

- [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
- [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
- [`transform`](transform.md)

Note: `skew` is not an independent `transform` value

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/rotate>

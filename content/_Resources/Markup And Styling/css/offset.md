offset
======

The `offset` CSS [shorthand property](shorthand_properties.md) sets all the
properties required for animating an element along a defined path. The
offset properties together help to define an *offset transform*, a
[transform](using_css_transforms.md) that aligns a point in
an element ([offset-anchor](offset-anchor.md)) to an *offset position*
([offset-position](offset-position.md)) on a path
([offset-path](offset-path.md)) at various points along the path
([offset-distance](offset-distance.md)) and optionally rotates the element
([offset-rotate](offset-rotate.md)) to follow the direction of the path.

**Note:** Early versions of the spec called this property `motion`.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`offset-anchor`](offset-anchor.md)
- [`offset-distance`](offset-distance.md)
- [`offset-path`](offset-path.md)
- [`offset-position`](offset-position.md)
- [`offset-rotate`](offset-rotate.md)

Syntax
------

[css]

```css
/* Offset position */
offset: auto;
offset: 10px 30px;
offset: none;

/* Offset path */
offset: ray(45deg closest-side);
offset: path("M 100 100 L 300 100 L 200 300 z");
offset: url(arc.svg);

/* Offset path with distance and/or rotation */
offset: url(circle.svg) 100px;
offset: url(circle.svg) 40%;
offset: url(circle.svg) 30deg;
offset: url(circle.svg) 50px 20deg;

/* Including offset anchor */
offset: ray(45deg closest-side) / 40px 20px;
offset: url(arc.svg) 2cm / 0.5cm 3cm;
offset: url(arc.svg) 30deg / 50px 100px;

/* Global values */
offset: inherit;
offset: initial;
offset: revert;
offset: revert-layer;
offset: unset;
```

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](offset-position.md): |
|                                   |     `auto`                        |
|                                   | -   [`offset-path`](offset-path.md): |
|                                   |     `none`                        |
|                                   | -   [](offset-distance.md): |
|                                   |     `0`                           |
|                                   | -                                 |
|                                   | [`offset-anchor`](offset-anchor.md): |
|                                   |     `auto`                        |
|                                   | -                                 |
|                                   | [`offset-rotate`](offset-rotate.md): |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | transformable elements            |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](offset-position.md): |
|                                   |     refer to the size of          |
|                                   |     containing block              |
|                                   | -   [](offset-distance.md): |
|                                   |     refer to the total path       |
|                                   |     length                        |
|                                   | -                                 |
|                                   | [`offset-anchor`](offset-anchor.md): |
|                                   |     relative to the width and the |
|                                   |     height of the element\'s      |
|                                   |     reference box                 |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](offset-position.md): |
|                                   |     for [`<length>`](length.md) the  |
|                                   |     absolute value, otherwise a   |
|                                   |     percentage                    |
|                                   | -   [`offset-path`](offset-path.md): |
|                                   |     as specified                  |
|                                   | -   [](offset-distance.md): |
|                                   |     for [`<length>`](length.md) the  |
|                                   |     absolute value, otherwise a   |
|                                   |     percentage                    |
|                                   | -                                 |
|                                   | [`offset-anchor`](offset-anchor.md): |
|                                   |     for [`<length>`](length.md) the  |
|                                   |     absolute value, otherwise a   |
|                                   |     percentage                    |
|                                   | -                                 |
|                                   | [`offset-rotate`](offset-rotate.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](offset-position.md): |
|                                   |     a                             |
|                                   |     [](position_value.md#interpolation) |
|                                   | -   [`offset-path`](offset-path.md): |
|                                   |     by computed value type        |
|                                   | -   [](offset-distance.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |   [length](length.md#interpolation), |
|                                   |     [](percentage.md#interpolation) |
|                                   |     or calc();                    |
|                                   | -                                 |
|                                   | [`offset-anchor`](offset-anchor.md): |
|                                   |     a                             |
|                                   |     [](position_value.md#interpolation) |
|                                   | -                                 |
|                                   | [`offset-rotate`](offset-rotate.md): |
|                                   |     as \<angle\>, \<basic-shape\> |
|                                   |     or \<path()\>                 |
+-----------------------------------+-----------------------------------+
| Creates [stacking                 | yes                               |
| cont                              |                                   |
| ext](css_positioned_layout/unders |                                   |
| tanding_z-index/stacking_context) |                                   |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
offset = 
  [ <'offset-position'>? [ <'offset-path'> [ <'offset-distance'> || <'offset-rotate'> ]? ]? ]! [ / <'offset-anchor'> ]?  
```

Examples
--------

### Animating an element along a path

#### HTML

[html]

```html
<div id="offsetElement"></div>
```

#### CSS

[css]

```css
@keyframes move {
  from {
    offset-distance: 0%;
  }

  to {
    offset-distance: 100%;
  }
}

#offsetElement {
  width: 50px;
  height: 50px;
  background-color: blue;
  offset: path("M 100 100 L 300 100 L 200 300 z") auto;
  animation: move 3s linear infinite;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [Motion Path Module Level 1\
  [\#
  offset-shorthand]](https://drafts.fxtf.org/motion/#offset-shorthand)

  ------------------------------------------------------------------------------

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

`offset`

5546

7979

72

No

4233

16

5546

5546

79

4233

16

6.05.0

See also
--------

- [`offset-anchor`](offset-anchor.md)
- [`offset-distance`](offset-distance.md)
- [`offset-path`](offset-path.md)
- [`offset-position`](offset-position.md)
- [`offset-rotate`](offset-rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/offset>

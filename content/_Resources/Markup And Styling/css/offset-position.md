offset-position
===============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `offset-position`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the initial position of an element along a path. This property is
typically used in combination with the [`offset-path`](offset-path.md)
property to create a motion effect. The value of `offset-position`
determines where the element gets placed initially for moving along an
`offset-path` if the offset-path function does not specify its own
starting position.

The `offset-position` property is part of a motion system based on
[`offset`](offset.md) constituent properties, including
[`offset-anchor`](offset-anchor.md), [`offset-distance`](offset-distance.md),
and `offset-path`. These properties work together to create various
motion effects along a path.

Syntax
------

[css]

```css
/* Keyword values */
offset-position: normal;
offset-position: auto;
offset-position: top;
offset-position: bottom;
offset-position: left;
offset-position: right;
offset-position: center;

/* <percentage> values */
offset-position: 25% 75%;

/* <length> values */
offset-position: 0 0;
offset-position: 1cm 2cm;
offset-position: 10ch 8em;

/* Edge offsets values */
offset-position: bottom 10px right 20px;
offset-position: right 3em bottom 10px;
offset-position: bottom 10px right;
offset-position: top right 10px;

/* Global values */
offset-position: inherit;
offset-position: initial;
offset-position: revert;
offset-position: revert-layer;
offset-position: unset;
```

### Values

[`normal`](#normal)

:   Indicates that the element does not have an offset starting position
    and places the element at `(50%, 50%)` of the containing block

[`auto`](#auto)

:   Indicates that the offset starting position is the top-left corner
    of the element\'s box. This is the default value.

[`<position>`](position_value.md)

:   Specifies the position as an x/y coordinate to place an element
    relative to its box edges. The position can be defined using one to
    four values. If two non-keyword values are used, the first value
    represents the horizontal position and the second represents the
    vertical position. If only one value is specified, the second value
    is assumed to be `center`. If three or four values are used, the
    [`<length-percentage>`](length-percentage.md) values are offsets for
    the preceding keyword value(s). For more explanation of these value
    types, see [`background-position`](background-position.md).

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to the size of containing block
  [Computed value](computed_value.md)   for [`<length>`](length.md) the absolute value, otherwise a percentage
  Animation type                     a [position](position_value.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------

Formal syntax
-------------

```
offset-position = 
  auto        |
  <position>  

<position> = 
  [ left | center | right ] || [ top | center | bottom ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]?  |
  [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ]  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting initial offset-position for an offset-path

In this example, the [`offset-path`](offset-path.md) property is used to
define the path along which the `cyan` element should move. The value of
the [`path()`](path.md) CSS function is an [SVG data
path](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/d) that
describes a curved path. The element moves along this curved path during
the `move` animation.

#### HTML

[html]

```html
<div id="wrap">
  <div id="motion-demo"></div>
</div>
```

#### CSS

[css]

```css
#motion-demo {
  offset-path: path("M20,20 C20,100 200,0 200,100");
  offset-position: left top;
  animation: move 3000ms infinite alternate ease-in-out;
  width: 40px;
  height: 40px;
  background: cyan;
}

@keyframes move {
  0%,
  20% {
    offset-distance: 0%;
  }
  80%,
  100% {
    offset-distance: 100%;
  }
}
```

#### Result

### Comparing various offset starting positions

This example visually compares various initial offset starting position
of an element when `ray()` is used to specify a value for the
[`offset-path`](offset-path.md) property. The number inside the element box
indicates the element to which CSS is applied as well as the element\'s
anchor point.

[css]

```css
.box {
  background-color: green;
  border-top: 6px dashed white;
  background-clip: border-box;
  position: absolute;
  top: 20px;
  left: 20px;
  opacity: 20%;
  color: white;
}

.box0 {
  offset-position: normal;
}

.box1 {
  offset-position: normal;
  offset-path: ray(0deg);
}

.box2 {
  offset-position: auto;
  offset-path: ray(0deg);
}

.box3 {
  offset-position: left top;
  offset-path: ray(0deg);
}

.box4 {
  offset-position: 30% 70%;
  offset-path: ray(120deg);
}
```

#### Result

Notice that when `offset-position` is `normal`, the starting position of
the ray is (`50%, 50%`) of the containing block. Also notice the
difference between offset starting positions `auto` and `left top`. The
value `auto` places the element such that its anchor point is at the
top-left corner of the element box itself, whereas the value `left top`
places the element such that the anchor point is the top-left corner of
the containing block.

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [Motion Path Module Level 1\
  [\#
  offset-position-property]](https://drafts.fxtf.org/motion/#offset-position-property)

  ----------------------------------------------------------------------------------------------

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

`offset-position`

116

116

116

No

102

16

116

116

No

No

16

No

`normal`

116

116

116

No

102

No

116

116

No

No

No

No

See also
--------

- [`offset`](offset.md)
- [`offset-anchor`](offset-anchor.md)
- [`offset-distance`](offset-distance.md)
- [`offset-path`](offset-path.md)
- [`offset-rotate`](offset-rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/offset-position>

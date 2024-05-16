offset-anchor
=============

The `offset-anchor`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the point inside the box of an element traveling along an
[`offset-path`](offset-path.md) that is actually moving along the path.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
offset-anchor: top;
offset-anchor: bottom;
offset-anchor: left;
offset-anchor: right;
offset-anchor: center;
offset-anchor: auto;

/* <percentage> values */
offset-anchor: 25% 75%;

/* <length> values */
offset-anchor: 0 0;
offset-anchor: 1cm 2cm;
offset-anchor: 10ch 8em;

/* Edge offsets values */
offset-anchor: bottom 10px right 20px;
offset-anchor: right 3em bottom 10px;

/* Global values */
offset-anchor: inherit;
offset-anchor: initial;
offset-anchor: revert;
offset-anchor: revert-layer;
offset-anchor: unset;
```

### Values

[`auto`](#auto)

:   `offset-anchor` is given the same value as the element\'s
    [`transform-origin`](transform-origin.md), unless
    [`offset-path`](offset-path.md) is `none`, in which case it takes its
    value from [`offset-position`](offset-position.md).

[`<position>`](#position)

:   A [`<position>`](position_value.md) defines an x/y coordinate, to place
    an item relative to the edges of an element\'s box. It can be
    defined using one to four values. For more specifics, see the
    [`<position>`](position_value.md) and
    [`background-position`](background-position.md) reference pages. Note
    that the 3-value position syntax does not work for any usage of
    `<position>`, except for in `background(-position)`.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  Percentages                        relative to the width and the height of the element\'s reference box
  [Computed value](computed_value.md)   for [`<length>`](length.md) the absolute value, otherwise a percentage
  Animation type                     a [position](position_value.md#interpolation)
  ---------------------------------- ----------------------------------------------------------------------

Formal syntax
-------------

```
offset-anchor = 
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

### Setting various offset-anchor values

In the following example, we have three
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
elements nested in
[`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)
elements. Each `<div>` is given the same [`offset-path`](offset-path.md) (a
horizontal line 200 pixels long) and animated to move along it. The
three are then given different [`background-color`](background-color.md)
and `offset-anchor` values.

Each `<section>` has been styled with a linear gradient to give it a
horizontal line running through its center, to give you a visual display
of where the `<div>`\'s offset paths are running.

This allows you to see what effect the different `offset-anchor` values
have --- the first one, `auto`, causes the `<div>`\'s center point to
move along the path. The other two cause the `<div>`\'s top-right and
bottom-left points to move along the path, respectively.

#### HTML

[html]

```html
<section>
  <div class="offset-anchor1"></div>
</section>
<section>
  <div class="offset-anchor2"></div>
</section>
<section>
  <div class="offset-anchor3"></div>
</section>
```

#### CSS

[css]

```css
div {
  offset-path: path("M 0,20 L 200,20");
  animation: move 3000ms infinite alternate ease-in-out;
  width: 40px;
  height: 40px;
}

section {
  background-image: linear-gradient(
    to bottom,
    transparent,
    transparent 49%,
    #000 50%,
    #000 51%,
    transparent 52%
  );
  border: 1px solid #ccc;
  margin-bottom: 10px;
}

.offset-anchor1 {
  offset-anchor: auto;
  background: cyan;
}

.offset-anchor2 {
  offset-anchor: right top;
  background: purple;
}

.offset-anchor3 {
  offset-anchor: left bottom;
  background: magenta;
}

@keyframes move {
  0% {
    offset-distance: 0%;
  }
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
  offset-anchor-property]](https://drafts.fxtf.org/motion/#offset-anchor-property)

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

`offset-anchor`

116

116

72

No

102

16

116

116

79

No

16

No

See also
--------

- [`offset`](offset.md)
- [`offset-distance`](offset-distance.md)
- [`offset-rotate`](offset-rotate.md)
- [SVG
    `<path>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/offset-anchor>

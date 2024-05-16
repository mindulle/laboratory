shape-margin
============

The `shape-margin`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets a
margin for a CSS shape created using [`shape-outside`](shape-outside.md).

Try it
------

The margin lets you adjust the distance between the edges of the shape
(the **float element**) and the surrounding content.

Syntax
------

[css]

```css
/* <length> values */
shape-margin: 10px;
shape-margin: 20mm;

/* <percentage> value */
shape-margin: 60%;

/* Global values */
shape-margin: inherit;
shape-margin: initial;
shape-margin: revert;
shape-margin: revert-layer;
shape-margin: unset;
```

### Values

[`<length-percentage>`](#length-percentage)

:   Sets the margin of the shape to a [`<length>`](length.md) value or to a
    [`<percentage>`](percentage.md) of the width of the element\'s
    containing block.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         floats
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
shape-margin = 
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Adding a margin to a polygon

#### HTML

[html]

```html
<section>
  <div class="shape"></div>
  We are not quite sure of any one thing in biology; our knowledge of geology is
  relatively very slight, and the economic laws of society are uncertain to
  every one except some individual who attempts to set them forth; but before
  the world was fashioned the square on the hypotenuse was equal to the sum of
  the squares on the other two sides of a right triangle, and it will be so
  after this world is dead; and the inhabitant of Mars, if one exists, probably
  knows its truth as we know it.
</section>
```

#### CSS

[css]

```css
section {
  max-width: 400px;
}

.shape {
  float: left;
  width: 150px;
  height: 150px;
  background-color: maroon;
  clip-path: polygon(0 0, 150px 150px, 0 150px);
  shape-outside: polygon(0 0, 150px 150px, 0 150px);
  shape-margin: 20px;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  shape-margin-property]](https://drafts.csswg.org/css-shapes/#shape-margin-property)

  ---------------------------------------------------------------------------------------------

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

`shape-margin`

37

79

62

No

24

10.110.1

37

37

62

24

10.3

3.0

See also
--------

- [CSS Shapes](css_shapes.md)
- [Overview of CSS Shapes](overview_of_shapes.md)
- [`shape-outside`](shape-outside.md)
- [`shape-image-threshold`](shape-image-threshold.md)
- [`<basic-shape>`](basic-shape.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/shape-margin>

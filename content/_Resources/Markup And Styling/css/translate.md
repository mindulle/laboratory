translate
=========

The `translate` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property allows you to specify translation transforms individually and
independently of the [`transform`](transform.md) property. This maps better
to typical user interface usage, and saves having to remember the exact
order of transform functions to specify in the `transform` value.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
translate: none;

/* Single values */
translate: 100px;
translate: 50%;

/* Two values */
translate: 100px 200px;
translate: 50% 105px;

/* Three values */
translate: 50% 105px 5rem;

/* Global values */
translate: inherit;
translate: initial;
translate: revert;
translate: revert-layer;
translate: unset;
```

### Values

[Single](#single) [`<length-percentage>`](length-percentage.md) value

:   A [`<length>`](length.md) or [`<percentage>`](percentage.md) that
    specifies a translation along the X-axis. Equivalent to a
    `translate()` (2D translation) function with a single value
    specified.

[Two](#two) [`<length-percentage>`](length-percentage.md) values

:   Two [`<length>`](length.md) or [`<percentage>`](percentage.md) that
    specify the X and Y axis translation values (respectively) of a 2D
    translation. Equivalent to a `translate()` (2D translation) function
    with two values specified.

[Three values](#three_values)

:   Two [`<length-percentage>`](length-percentage.md) and single
    [`<length>`](length.md) values that specify the X, Y, and Z axis
    translation values (respectively) of a 3D translation. Equivalent to
    a `translate3d()` (3D translation) function.

[`none`](#none)

:   Specifies that no translation should be applied.

Formal definition
-----------------

  ------------------------------------------------------------------------------------------ -------------------------------------------------------------------------
  [Initial value](initial_value.md)                                                             `none`
  Applies to                                                                                 transformable elements
  [Inherited](inheritance.md)                                                                   no
  Percentages                                                                                refer to the size of bounding box
  [Computed value](computed_value.md)                                                           as specified, but with relative lengths converted into absolute lengths
  Animation type                                                                             a transform
  Creates [stacking context](stacking_context.md)   yes
  ------------------------------------------------------------------------------------------ -------------------------------------------------------------------------

Formal syntax
-------------

```
translate = 
  none                                                |
  <length-percentage> [ <length-percentage> <length>? ]?  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Translating an element on hover

This example shows how to use the `translate` property to move an
element in three axes. The first box is moved along the X axis and the
second box is moved along the X and Y axes. The third box is moved along
the X, Y and Z axes and has the appearance of moving toward the viewer
because of the addition of [`perspective`](_Resources/Markup%20And%20Styling/css/perspective.md) to the parent
element.

#### HTML

[html]

```html
<div class="wrapper">
  <div id="box1">translate X</div>
  <div id="box2">translate X,Y</div>
  <div id="box3">translate X,Y,Z</div>
</div>
```

#### CSS

[css]

```css
.wrapper {
  perspective: 100px;
  display: inline-flex;
  gap: 1em;
}
.wrapper > div {
  width: 7em;
  line-height: 7em;
  text-align: center;
  transition: 0.5s ease-in-out;
  border: 3px dotted;
}
#box1:hover {
  translate: 20px;
}

#box2:hover {
  translate: 20px 20px;
}

#box3:hover {
  translate: 5px 5px 30px;
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

`translate`

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

- [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
- [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)
- [`transform`](transform.md)

Note: skew is not an independent transform value

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/translate>

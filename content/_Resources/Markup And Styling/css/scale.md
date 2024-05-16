scale
=====

The `scale` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property allows you to specify scale transforms individually and
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
scale: none;

/* Single values */
/* values of more than 1 or 100% make the element grow */
scale: 2;
/* values of less than 1 or 100% make the element shrink */
scale: 50%;

/* Two values */
scale: 2 0.5;

/* Three values */
scale: 200% 50% 200%;

/* Global values */
scale: inherit;
scale: initial;
scale: revert;
scale: revert-layer;
scale: unset;
```

### Values

[Single value](#single_value)

:   A [`<number>`](number.md) or [`<percentage>`](percentage.md) specifying a
    scale factor to make the affected element scale by the same factor
    along both the X and Y axes. Equivalent to a `scale()` (2D scaling)
    function with a single value specified.

[Two values](#two_values)

:   Two [`<number>`](number.md) or [`<percentage>`](percentage.md) values that
    specify the X and Y axis scaling values (respectively) of a 2D
    scale. Equivalent to a `scale()` (2D scaling) function with two
    values specified.

[Three values](#three_values)

:   Three [`<number>`](number.md) or [`<percentage>`](percentage.md) values
    that specify the X, Y, and Z axis scaling values (respectively) of a
    3D scale. Equivalent to a `scale3d()` (3D scaling) function.

[`none`](#none)

:   Specifies that no scaling should be applied.

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
scale = 
  none                              |
  [ <number> | <percentage> ]  
```

Examples
--------

### Scaling an element on hover

The following example shows how to scale an element on hover. Two boxes
are shown, one with a single `scale` value which scales the element
along both axes. The second box has two `scale` values which scales the
element along the X and Y axes independently.

#### HTML

[html]

```html
<div class="box" id="box1">single value</div>
<div class="box" id="box2">two values</div>
```

#### CSS

[css]

```css
.box {
  float: left;
  margin: 1em;
  width: 7em;
  line-height: 7em;
  text-align: center;
  transition: 0.5s ease-in-out;
  border: 3px dotted;
}

#box1:hover {
  scale: 1.25;
}

#box2:hover {
  scale: 1.25 0.75;
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

`scale`

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
- [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)
- [`transform`](transform.md)

Note: skew is not an independent transform value

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scale>

border-top-left-radius
======================

The `border-top-left-radius`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property rounds
the top-left corner of an element by specifying the radius (or the
radius of the semi-major and semi-minor axes) of the ellipse defining
the curvature of the corner.

Try it
------

The rounding can be a circle or an ellipse, or if one of the value is
`0`, no rounding is done and the corner is square.

A background, being an image or a color, is clipped at the border, even
a rounded one; the exact location of the clipping is defined by the
value of the [`background-clip`](background-clip.md) property.

**Note:** If the value of this property is not set in a
[`border-radius`](border-radius.md) shorthand property that is applied to
the element after the `border-top-left-radius` CSS property, the value
of this property is then reset to its initial value by the [](shorthand_properties.md).

Syntax
------

[css]

```css
/* the corner is a circle */
/* border-top-left-radius: radius */
border-top-left-radius: 3px;

/* the corner is an ellipse */
/* border-top-left-radius: horizontal vertical */
border-top-left-radius: 0.5em 1em;

border-top-left-radius: inherit;

/* Global values */
border-top-left-radius: inherit;
border-top-left-radius: initial;
border-top-left-radius: revert;
border-top-left-radius: revert-layer;
border-top-left-radius: unset;
```

With one value:

- the value is a [`<length>`](length.md) or a
    [`<percentage>`](percentage.md) denoting the radius of the circle to
    use for the border in that corner.

With two values:

- the first value is a [`<length>`](length.md) or a
    [`<percentage>`](percentage.md) denoting the horizontal semi-major axis
    of the ellipse to use for the border in that corner.
- the second value is a [`<length>`](length.md) or a
    [`<percentage>`](percentage.md) denoting the vertical semi-major axis
    of the ellipse to use for the border in that corner.

### Values

[`<length-percentage>`](#length-percentage)

:   Denotes the size of the circle radius or the semi-major and
    semi-minor axes of the ellipse. As absolute length it can be
    expressed in any unit allowed by the CSS [`<length>`](length.md) data
    type. Percentages for the horizontal axis refer to the width of the
    box, percentages for the vertical axis refer to the height of the
    box. Negative values are invalid.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements; but User Agents are not required to apply to `table` and `inline-table` elements when [`border-collapse`](border-collapse.md) is `collapse`. The behavior on internal table elements is undefined for the moment.. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the corresponding dimension of the border box
  [Computed value](computed_value.md)   two absolute [`<length>`](length.md)s or [`<percentage>`](percentage.md)s
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-top-left-radius = 
  <length-percentage [0,∞]>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Arc of a circle

A single `<length>` value produces an arc of a circle.

[css]

```css
div {
  border-top-left-radius: 40px;
  background-color: lightgreen;
  border: solid 1px black;
  width: 100px;
  height: 100px;
}
```

### Arc of an ellipse

Two different `<length>` values produce an arc of an ellipse.

[css]

```css
div {
  border-top-left-radius: 40px 20px;
  background-color: lightgreen;
  border: solid 1px black;
  width: 100px;
  height: 100px;
}
```

### Square element with percentage radius

A square element with a single `<percentage>` value produces an arc of a
circle.

[css]

```css
div {
  border-top-left-radius: 40%;
  background-color: lightgreen;
  border: solid 1px black;
  width: 100px;
  height: 100px;
}
```

### Non-square element with percentage radius

A non-square element with a single `<percentage>` value produces an arc
of an ellipse.

[css]

```css
div {
  border-top-left-radius: 40%;
  background-color: lightgreen;
  border: solid 1px black;
  width: 200px;
  height: 100px;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-radius]](https://drafts.csswg.org/css-backgrounds/#the-border-radius)

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

`border-top-left-radius`

41

1212

49

4Before Firefox 50, border styles of rounded corners were always
rendered as if `border-style` was solid. This has been fixed in Firefox
50.

1--12

9

1510.5

53

≤37≤37

1818

49

4Before Firefox 50, border styles of rounded corners were always
rendered as if `border-style` was solid. This has been fixed in Firefox
50.

4--14

1411

4.21

1.01.0

`elliptical_corners`

1

12

3.5

9

10.5

3

≤37

18

4

14

1

1.0

`percentages`

4

12

4

1--4Before Firefox 4, the
[`<percentage>`](https://developer.mozilla.org/docs/Web/CSS/percentage)
was relative to the width of the box even when specifying the radius for
a height. This implied that `-moz-border-radius-bottomright` was always
drawing an arc of circle, and never an ellipse, when followed by a
single value.

9

10.5

5

≤37

18

4

14

4.2

1.0

See also
--------

- [`border-radius`](border-radius.md) shorthand property
- [`border-top-right-radius`](border-top-right-radius.md),
    [`border-bottom-right-radius`](border-bottom-right-radius.md), and
    [`border-bottom-left-radius`](border-bottom-left-radius.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-left-radius>

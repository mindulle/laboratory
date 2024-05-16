\<position\>
============

The `<position>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) denotes a two-dimensional coordinate used to set
a location relative to an element box. It is used in the
[`background-position`](background-position.md),
[`object-position`](object-position.md), [`mask-position`](mask-position.md)
[`offset-position`](offset-position.md), [`offset-anchor`](offset-anchor.md)
and [`transform-origin`](transform-origin.md) properties.

**Note:** The final position described by the `<position>` value does
not need to be inside the element\'s box.

Syntax
------

The `<position>` data type is specified with one or two keywords, with
optional offsets.

The keyword values are `center`, `top`, `right`, `bottom`, and `left`.
Each keyword represents either an edge of the element\'s box or the
center line between two edges. Depending on the context, `center`
represents either the center between the left and right edges, or the
center between the top and bottom edges.

If specified, an offset can be either a relative
[`<percentage>`](percentage.md) value or an absolute [`<length>`](length.md)
value. Positive values are offset towards the right or the bottom,
whichever is appropriate. Negative values are offset in the opposite
directions.

If only a single offset value is specified, it defines the x-coordinate,
with the value for the other axis defaulting to `center`.

[css]

```css
/* 1-value syntax */
keyword                  /* Either the horizontal or vertical position; the other axis defaults to center */
value                    /* The position on the x-axis; the y-axis defaults to 50% */

/* 2-value syntax */
keyword keyword          /* A keyword for each direction (the order is irrelevant) */
keyword value            /* A keyword for horizontal position, value for vertical position */
value keyword            /* A value for horizontal position, keyword for vertical position */
value value              /* A value for each direction (horizontal then vertical) */

/* 4-value syntax */
keyword value keyword value /* Each value is an offset from the keyword that precedes it */
```

**Note:** The [`background-position`](background-position.md) property also
accepts a three-value syntax. This is not allowed in other properties
that use `<position>`.

Interpolation
-------------

When animated, a point\'s abscissa and ordinate values are interpolated
independently. However, because the speed of the interpolation is
determined by a single [easing function](easing-function.md) for both
coordinates, the point will move in a straight line.

Formal syntax
-------------

```
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

### Valid positions

```
center
left
center top

right 8.5%
bottom 12vmin right -6px

10% 20%
8rem 14px
```

### Invalid positions

```
left right
bottom top
10px 15px 20px 15px
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# position]](https://drafts.csswg.org/css-values/#position)

  -----------------------------------------------------------------------

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

`position_value`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

`four_value_syntax`

25

12

13

9

10.5

7

4.4

25

14

14

7

1.5

`keyword_value_syntax`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

See also
--------

- [CSS Values and Units](css_values_and_units.md)
- [CSS Values and Units
    introduction](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [`background-position`](background-position.md)
- [`radial-gradient()`](radial-gradient.md)
- [`conic-gradient()`](conic-gradient.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/position_value>

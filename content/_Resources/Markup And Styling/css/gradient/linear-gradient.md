linear-gradient()
=================

The `linear-gradient()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) creates an image consisting of a
progressive transition between two or more colors along a straight line.
Its result is an object of the [`<gradient>`](gradient.md) data type,
which is a special kind of [`<image>`](_Resources/Markup%20And%20Styling/css/image.md).

Try it
------

Syntax
------

[css]

```css
/* A gradient tilted 45 degrees,
   starting blue and finishing red */
linear-gradient(45deg, blue, red);

/* A gradient going from the bottom right to the top left corner,
   starting blue and finishing red */
linear-gradient(to left top, blue, red);

/* Color stop: A gradient going from the bottom to top,
   starting blue, turning green at 40% of its length,
   and finishing red */
linear-gradient(0deg, blue, green 40%, red);

/* Color hint: A gradient going from the left to right,
   starting red, getting to the midpoint color
   10% of the way across the length of the gradient,
   taking the rest of the 90% of the length to change to blue */
linear-gradient(.25turn, red, 10%, blue);

/* Multi-position color stop: A gradient tilted 45 degrees,
   with a red bottom-left half and a blue top-right half,
   with a hard line where the gradient changes from red to blue */
linear-gradient(45deg, red 0 50%, blue 50% 100%);
```

### Values

[`<side-or-corner>`](#side-or-corner)

:   The position of the gradient line\'s starting point. If specified,
    it consists of the word `to` and up to two keywords: one indicates
    the horizontal side (`left` or `right`), and the other the vertical
    side (`top` or `bottom`). The order of the side keywords does not
    matter. If unspecified, it defaults to `to bottom`.

    The values `to top`, `to bottom`, `to left`, and `to right` are
    equivalent to the angles `0deg`, `180deg`, `270deg`, and `90deg`,
    respectively. The other values are translated into an angle.

[`<angle>`](angle.md)

:   The gradient line\'s angle of direction. A value of `0deg` is
    equivalent to `to top`; increasing values rotate clockwise from
    there.

[`<linear-color-stop>`](#linear-color-stop)

:   A color-stop\'s [`<color>`](color_value.md) value, followed by one
    or two optional stop positions, (each being either a
    [`<percentage>`](percentage.md) or a [`<length>`](length.md) along
    the gradient\'s axis).

[`<color-hint>`](#color-hint)

:   An interpolation hint defining how the gradient progresses between
    adjacent color stops. The length defines at which point between two
    color stops the gradient color should reach the midpoint of the
    color transition. If omitted, the midpoint of the color transition
    is the midpoint between two color stops.

**Note:** Rendering of [color stops in CSS
gradients](#composition_of_a_linear_gradient) follows the same rules as
color stops in [SVG
gradients](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients).

Description
-----------

As with any gradient, a linear gradient has [](_Resources/Markup%20And%20Styling/css/image.md#description); i.e., it has no natural or preferred
size, nor a preferred ratio. Its concrete size will match the size of
the element it applies to.

To create a linear gradient that repeats to fill its container, use the
[`repeating-linear-gradient()`](repeating-linear-gradient.md) function
instead.

Because `<gradient>`s belong to the `<image>` data type, they can only
be used where [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)s can be used. For this reason,
`linear-gradient()` won\'t work on
[`background-color`](background-color.md) and other properties that use
the [`<color>`](color_value.md) data type.

### Composition of a linear gradient

A linear gradient is defined by an axis---the *gradient line*---and two
or more *color-stop points*. Each point on the axis is a distinct color;
to create a smooth gradient, the `linear-gradient()` function draws a
series of colored lines perpendicular to the gradient line, each one
matching the color of the point where it intersects the gradient line.

The gradient line is defined by the center of the box containing the
gradient image and by an angle. The colors of the gradient are
determined by two or more points: the starting point, the ending point,
and, in between, optional color-stop points.

The *starting point* is the location on the gradient line where the
first color begins. The *ending point* is the point where the last color
ends. Each of these two points is defined by the intersection of the
gradient line with a perpendicular line passing from the box corner
which is in the same quadrant. The ending point can be understood as the
symmetrical point of the starting point. These somewhat complex
definitions lead to an interesting effect sometimes called *magic
corners*: the corners nearest to the starting and ending points have the
same color as their respective starting or ending points.

#### Customizing Gradients

By adding more color-stop points on the gradient line, you can create a
highly customized transition between multiple colors. A color-stop\'s
position can be explicitly defined by using a [`<length>`](length.md) or
a [`<percentage>`](percentage.md). If you don\'t specify the location of
a color, it is placed halfway between the one that precedes it and the
one that follows it. The following two gradients are equivalent.

[css]

```css
linear-gradient(red, orange, yellow, green, blue);
linear-gradient(red 0%, orange 25%, yellow 50%, green 75%, blue 100%);
```

By default, colors transition smoothly from the color at one color-stop
to the color at the subsequent color-stop, with the midpoint between the
colors being the halfway point between the color transition. You can
move this midpoint to any position between two color-stops by adding an
unlabelled % color hint between the two colors to indicate where the
middle of the color transition should be. The following example is solid
red from the start to the 10% mark and solid blue from 90% to the end.
Between 10% and 90% the color transitions from red to blue, however, the
midpoint of the transition is at the 30% mark rather than 50% as would
have happened without the 30% color hint.

[css]

```css
linear-gradient(red 10%, 30%, blue 90%);
```

If two or more color-stops are at the same location, the transition will
be a hard line between the first and last colors declared at that
location.

Color-stops should be listed in ascending order. Subsequent color-stops
of lower value will override the value of the previous color-stop
creating a hard transition. The following changes from red to yellow at
the 40% mark, and then transitions from yellow to blue over 25% of the
gradient:

[css]

```css
linear-gradient(red 40%, yellow 30%, blue 65%);
```

Multi-position color-stops are allowed. A color can be declared as two
adjacent color-stops by including both positions in the CSS declaration.
The following three gradients are equivalent:

[css]

```css
linear-gradient(red 0%, orange 10%, orange 30%, yellow 50%, yellow 70%, green 90%, green 100%);
linear-gradient(red, orange 10% 30%, yellow 50% 70%, green 90%);
linear-gradient(red 0%, orange 10% 30%, yellow 50% 70%, green 90% 100%);
```

By default, if there is no color with a `0%` stop, the first color
declared will be at that point. Similarly, the last color will continue
to the `100%` mark, or be at the `100%` mark if no length has been
declared on that last stop.

Formal syntax
-------------

```
<linear-gradient()> = 
  linear-gradient( [ <angle> | to <side-or-corner> ]? , <color-stop-list> )  

<side-or-corner> = 
  [ left | right ]  ||
  [ top | bottom ]  

<color-stop-list> = 
  <linear-color-stop> , [ <linear-color-hint>? , <linear-color-stop> ]#  

<linear-color-stop> = 
  <color>               &&
  <length-percentage>?  

<linear-color-hint> = 
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Gradient at a 45-degree angle

[css]

```css
body {
  background: linear-gradient(45deg, red, blue);
}
```

### Gradient that starts at 60% of the gradient line

[css]

```css
body {
  background: linear-gradient(135deg, orange 60%, cyan);
}
```

### Gradient with multi-position color-stops

This example uses multi-position color-stops, with adjacent colors
having the same color-stop value, creating a striped effect.

[css]

```css
body {
  background: linear-gradient(
    to right,
    red 20%,
    orange 20% 40%,
    yellow 40% 60%,
    green 60% 80%,
    blue 80%
  );
}
```

### More linear-gradient examples

Please see [using CSS gradients](using_css_gradients.md) for
more examples.

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Images Module Level 4\
  [\#
  linear-gradients]](https://drafts.csswg.org/css-images-4/#linear-gradients)

  -------------------------------------------------------------------------------------

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

`linear-gradient`

2610

12

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

3.6\[\"Since Firefox 42, the prefixed version of gradients can be
disabled by setting `layout.css.prefixes.gradients` to `false`.\",
\"Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.\"\]

10Internet Explorer 5.5 through 9.0 supported gradients via a
proprietary filter:
`-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

15Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.

12.1

11--15Considers `<angle>` to start to the right, instead of the top.
I.e. it considered an angle of `0deg` as a direction indicator pointing
to the right.

7

5.1\[\"Safari 4 was supporting an experimental
`-webkit-gradient(linear,…)` function. It is more limited than the later
standard version: you cannot specify both a position and an angle like
in `linear-gradient()`. This old outdated syntax is still supported for
compatibility purposes.\", \"Considers `<angle>` to start to the right,
instead of the top. I.e. it considered an angle of `0deg` as a direction
indicator pointing to the right.\"\]

≤37≤37

2618

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

4\[\"Since Firefox 42, the prefixed version of gradients can be disabled
by setting `layout.css.prefixes.gradients` to `false`.\", \"Considers
`<angle>` to start to the right, instead of the top. I.e. it considered
an angle of `0deg` as a direction indicator pointing to the right.\"\]

14Considers `<angle>` to start to the right, instead of the top. I.e. it
considered an angle of `0deg` as a direction indicator pointing to the
right.

12.1

11--14Considers `<angle>` to start to the right, instead of the top.
I.e. it considered an angle of `0deg` as a direction indicator pointing
to the right.

7

5\[\"Safari 4 was supporting an experimental
`-webkit-gradient(linear,…)` function. It is more limited than the later
standard version: you cannot specify both a position and an angle like
in `linear-gradient()`. This old outdated syntax is still supported for
compatibility purposes.\", \"Considers `<angle>` to start to the right,
instead of the top. I.e. it considered an angle of `0deg` as a direction
indicator pointing to the right.\"\]

1.51.0

`doubleposition`

71

79

64

No

58

12.1

71

71

64

50

12.2

10.0

`hue_interpolation_method`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

`interpolation_color_space`

111

111

No

No

97

16.2

111

111

No

No

16.2

22.0

`interpolation_hints`

40

79

36

No

27

7

40

40

36

27

7

4.0

`to`

26

12

10

10

12.1

7

4.4

26

10

14

7

1.5

`unitless_0_angle`

26

12

55

46Accepted only in `-webkit-linear-gradient()` and
`-moz-linear-gradient()`, not `linear-gradient()`.

No

16

7

4.4

26

55

46Accepted only in `-webkit-linear-gradient()` and
`-moz-linear-gradient()`, not `linear-gradient()`.

14

7

1.5

See also
--------

- [Using CSS gradients](using_css_gradients.md)
- Other gradient functions:
    [`repeating-linear-gradient()`](repeating-linear-gradient.md),
    [`radial-gradient()`](radial-gradient.md),
    [`repeating-radial-gradient()`](repeating-radial-gradient.md),
    [`conic-gradient()`](conic-gradient.md),
    [`repeating-conic-gradient()`](repeating-conic-gradient.md)
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [`element()`](element().md)
- [`image()`](_Resources/Markup%20And%20Styling/css/image/image.md)
- [`image-set()`](image-set.md)
- [`cross-fade()`](cross-fade.md)
- [CSS images module](css_images.md)
- [New functions, gradients, and hues in CSS colors
    (Level 4)](https://developer.mozilla.org/en-US/blog/css-color-module-level-4/)
    on MDN blog (2023)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/linear-gradient>

repeating-linear-gradient()
===========================

The `repeating-linear-gradient()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) creates an image consisting of repeating
linear gradients. It is similar to
[`linear-gradient()`](linear-gradient.md) and takes the same arguments, but
it repeats the color stops infinitely in all directions so as to cover
its entire container. The function\'s result is an object of the
[`<gradient>`](gradient.md) data type, which is a special kind of
[`<image>`](_Resources/Markup%20And%20Styling/css/image.md).

Try it
------

The length of the gradient that repeats is the distance between the
first and last color stop. If the first color does not have a
color-stop-length, the color-stop-length defaults to 0. With each
repetition, the positions of the color stops are shifted by a multiple
of the length of the basic linear gradient. Thus, the position of each
ending color stop coincides with a starting color stop; if the color
values are different, this will result in a sharp visual transition.
This can be altered with repeating the first color again as the last
color.

As with any gradient, a repeating linear gradient has [](_Resources/Markup%20And%20Styling/css/image.md#description); i.e., it has no natural or preferred
size, nor a preferred ratio. Its concrete size will match the size of
the element it applies to.

Because `<gradient>`s belong to the `<image>` data type, they can only
be used where `<image>`s can be used. For this reason,
`repeating-linear-gradient()` won\'t work on
[`background-color`](background-color.md) and other properties that use
the [`<color>`](color_value.md) data type.

Syntax
------

[css]

```css
/* A repeating gradient tilted 45 degrees,
   starting blue and finishing red, repeating 3 times */
repeating-linear-gradient(45deg, blue, red 33.3%);

/* A repeating gradient going from the bottom right to the top left,
   starting blue and finishing red, repeating every 20px */
repeating-linear-gradient(to left top, blue, red 20px);

/* A gradient going from the bottom to top,
   starting blue, turning green after 40%,
   and finishing red. This gradient doesn't repeat because
   the last color stop defaults to 100% */
repeating-linear-gradient(0deg, blue, green 40%, red);

/* A gradient repeating five times, going from the left to right,
   starting red, turning green, and back to red */
repeating-linear-gradient(to right, red 0%, green 10%, red 20%);
```

### Values

[`<side-or-corner>`](#side-or-corner)

:   The position of the gradient line\'s starting point. If specified,
    it consists of the word `to` and up to two keywords: one indicates
    the horizontal side (`left` or `right`), and the other the vertical
    side (`top` or `bottom`). The order of the side keywords does not
    matter. If unspecified, it defaults to `to bottom`.

    The values `to top`, `to bottom`, `to left`, and `to right` are
    equivalent to the angles `0deg`, `180deg`, `270deg`, and `90deg`
    respectively. The other values are translated into an angle.

[`<angle>`](angle.md)

:   The gradient line\'s angle of direction. A value of `0deg` is
    equivalent to `to top`; increasing values rotate clockwise from
    there.

[`<linear-color-stop>`](#linear-color-stop)

:   A color-stop\'s [`<color>`](color_value.md) value, followed by one
    or two optional stop positions, (each being either a
    [`<percentage>`](percentage.md) or a [`<length>`](length.md) along
    the gradient\'s axis). A percentage of `0%`, or a length of `0`,
    represents the start of the gradient; the value `100%` is 100% of
    the image size, meaning the gradient will not repeat.

[`<color-hint>`](#color-hint)

:   The color-hint is an interpolation hint defining how the gradient
    progresses between adjacent color stops. The length defines at which
    point between two color stops the gradient color should reach the
    midpoint of the color transition. If omitted, the midpoint of the
    color transition is the midpoint between two color stops.

**Note:** Rendering of [color stops in CSS
gradients](#gradient_with_multiple_color_stops) follows the same rules
as color stops in [SVG
gradients](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients).

### Formal syntax

Error: could not find syntax for this item

Examples
--------

### Zebra stripes

[css]

```css
body {
  background-image: repeating-linear-gradient(
    -45deg,
    transparent,
    transparent 20px,
    black 20px,
    black 40px
  );
  /* with multiple color stop lengths */
  background-image: repeating-linear-gradient(
    -45deg,
    transparent 0 20px,
    black 20px 40px
  );
}
```

### Ten repeating horizontal bars

[css]

```css
body {
  background-image: repeating-linear-gradient(
    to bottom,
    rgb(26, 198, 204),
    rgb(26, 198, 204) 7%,
    rgb(100, 100, 100) 10%
  );
}
```

Because the last color stop is 10% and the gradient is vertical, each
gradient in the repeated gradient is 10% of the height, fitting 10
horizontal bars.

**Note:** Please see [](using_css_gradients.md) for more examples.

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Images Module Level 3\
  [\#
  repeating-gradients]](https://drafts.csswg.org/css-images/#repeating-gradients)

  -----------------------------------------------------------------------------------------

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

`repeating-linear-gradient`

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
in `repeating-linear-gradient()`. This old outdated syntax is still
supported for compatibility purposes.\", \"Considers `<angle>` to start
to the right, instead of the top. I.e. it considered an angle of `0deg`
as a direction indicator pointing to the right.\"\]

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
in `repeating-linear-gradient()`. This old outdated syntax is still
supported for compatibility purposes.\", \"Considers `<angle>` to start
to the right, instead of the top. I.e. it considered an angle of `0deg`
as a direction indicator pointing to the right.\"\]

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

46Accepted only in `-webkit-repeating-linear-gradient()` and
`-moz-repeating-linear-gradient()`, not `repeating-linear-gradient()`.

No

16

7

4.4

26

55

46Accepted only in `-webkit-repeating-linear-gradient()` and
`-moz-repeating-linear-gradient()`, not `repeating-linear-gradient()`.

14

7

1.5

See also
--------

- [Using CSS gradients](using_css_gradients.md)
- Other gradient functions: [`linear-gradient()`](linear-gradient.md),
    [`radial-gradient()`](radial-gradient.md),
    [`repeating-radial-gradient()`](repeating-radial-gradient.md),
    [`conic-gradient()`](conic-gradient.md),
    [`repeating-conic-gradient()`](repeating-conic-gradient.md)
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [`image()`](_Resources/Markup%20And%20Styling/css/image/image.md)
- [`element()`](element().md)
- [`image-set()`](image-set.md)
- [`cross-fade()`](cross-fade.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-linear-gradient>

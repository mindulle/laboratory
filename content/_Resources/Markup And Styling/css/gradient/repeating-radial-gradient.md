repeating-radial-gradient()
===========================

The `repeating-radial-gradient()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) creates an image consisting of repeating
gradients that radiate from an origin. It is similar to
[`radial-gradient()`](radial-gradient.md) and takes the same arguments, but
it repeats the color stops infinitely in all directions so as to cover
its entire container, similar to
[`repeating-linear-gradient()`](repeating-linear-gradient.md). The
function\'s result is an object of the [`<gradient>`](gradient.md) data
type, which is a special kind of [`<image>`](_Resources/Markup%20And%20Styling/css/image.md).

Try it
------

With each repetition, the positions of the color stops are shifted by a
multiple of the dimensions of the basic radial gradient (the distance
between the last color stop and the first). Thus, the position of each
ending color stop coincides with a starting color stop; if the color
values are different, this will result in a sharp visual transition,
which can be mitigated by repeating the first color as the last color.

As with any gradient, a repeating radial gradient has [](_Resources/Markup%20And%20Styling/css/image.md#description); i.e., it has no natural or preferred
size, nor a preferred ratio. Its concrete size will match the size of
the element it applies to.

Because `<gradient>`s belong to the `<image>` data type, they can only
be used where `<image>`s can be used. For this reason,
`repeating-radial-gradient()` won\'t work on
[`background-color`](background-color.md) and other properties that use
the [`<color>`](color_value.md) data type.

Syntax
------

[css]

```css
/* A gradient at the center of its container,
   starting red, changing to blue, and finishing green,
   with the colors repeating every 30px */
repeating-radial-gradient(circle at center, red 0, blue, green 30px);

/* An elliptical gradient near the top left of its container,
   starting red, changing to green and back again,
   repeating five times between the center and the bottom right corner,
   and only once between the center and the top left corner */
repeating-radial-gradient(farthest-corner at 20% 20%, red 0, green, red 20%);
```

### Values

[`<position>`](position_value.md)

:   The position of the gradient, interpreted in the same way as
    [`background-position`](background-position.md) or
    [`transform-origin`](transform-origin.md). If unspecified, it
    defaults to `center`.

[`<shape>`](#shape)

:   The gradient\'s shape. The value can be `circle` (meaning that the
    gradient\'s shape is a circle with constant radius) or `ellipse`
    (meaning that the shape is an axis-aligned ellipse). If unspecified,
    it defaults to `ellipse`.

[`<extent-keyword>`](#extent-keyword)

:   A keyword describing how big the ending shape must be. The possible
    values are:

      Keyword             Description
      ------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
      `closest-side`      The gradient\'s ending shape meets the side of the box closest to its center (for circles) or meets both the vertical and horizontal sides closest to the center (for ellipses).
      `closest-corner`    The gradient\'s ending shape is sized so that it exactly meets the closest corner of the box from its center.
      `farthest-side`     Similar to `closest-side`, except the ending shape is sized to meet the side of the box farthest from its center (or vertical and horizontal sides).
      `farthest-corner`   The gradient\'s ending shape is sized so that it exactly meets the farthest corner of the box from its center.
    

    
    **Note:** Early implementations of this function included other
    keywords (`cover` and `contain`) as synonyms of the standard
    `farthest-corner` and `closest-side`, respectively. Use the standard
    keywords only, as some implementations have already dropped those
    older variants.

[`<color-stop>`](#color-stop)

:   A color-stop\'s [`<color>`](color_value.md) value, followed by an
    optional stop position (either a [`<percentage>`](percentage.md) or
    a [`<length>`](length.md) along the gradient\'s axis). A percentage
    of `0%`, or a length of `0`, represents the center of the gradient;
    the value `100%` represents the intersection of the ending shape
    with the virtual gradient ray. Percentage values in between are
    linearly positioned on the virtual gradient ray.

### Formal syntax

Error: could not find syntax for this item

Examples
--------

### Black and white gradient

[css]

```css
.radial-gradient {
  background: repeating-radial-gradient(
    black,
    black 5px,
    white 5px,
    white 10px
  );
}
```

### Farthest-corner

[css]

```css
.radial-gradient {
  background: repeating-radial-gradient(
    ellipse farthest-corner at 20% 20%,
    red,
    black 5%,
    blue 5%,
    green 10%
  );
  background: repeating-radial-gradient(
    ellipse farthest-corner at 20% 20%,
    red 0 5%,
    green 5% 10%
  );
}
```

The elliptical gradient will be centered 20% from the top left, and will
repeat 10 times between the center and the farthest corner (the bottom
right corner). Browsers supporting multi position color stops will
display a red and green striped ellipse. Browsers not supporting the
syntax yet will see a gradient that goes from red to black and then from
blue to green.

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

`repeating-radial-gradient`

2610

12

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

3.6Since Firefox 42, the prefixed version of gradients can be disabled
by setting `layout.css.prefixes.gradients` to `false`.

10

1512.112--15

7

5.1Safari 4 was supporting an experimental `-webkit-gradient(radial,…)`
function. This old outdated syntax is still supported for compatibility
purposes.

≤374.4

2618

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

10Since Firefox 42, the prefixed version of gradients can be disabled by
setting `layout.css.prefixes.gradients` to `false`.

1412.112--14

7

5Safari 4 was supporting an experimental `-webkit-gradient(radial,…)`
function. This old outdated syntax is still supported for compatibility
purposes.

1.51.0

`at`

26

12

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

10Since Firefox 42, the prefixed version of gradients can be disabled by
setting `layout.css.prefixes.gradients` to `false`.

10

1512--15

7

4.4

26

49

16Before Firefox 36, gradients weren\'t applied on the pre-multiplied
color space, leading to shades of grey unexpectedly appearing when used
with transparency.

10Since Firefox 42, the prefixed version of gradients can be disabled by
setting `layout.css.prefixes.gradients` to `false`.

1412--14

7

1.5

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

46

27

7

4.0

See also
--------

- [Using CSS gradients](using_css_gradients.md)
- Other gradient functions: [`radial-gradient()`](radial-gradient.md),
    [`linear-gradient()`](linear-gradient.md),
    [`repeating-linear-gradient()`](repeating-linear-gradient.md),
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
https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/repeating-radial-gradient>

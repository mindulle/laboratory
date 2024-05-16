conic-gradient()
================

The `conic-gradient()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) creates an image consisting of a gradient
with color transitions rotated around a center point (rather than
radiating from the center). Example conic gradients include pie charts
and [color
wheels](https://developer.mozilla.org/en-US/docs/Glossary/Color_wheel).
The result of the `conic-gradient()` function is an object of the
[`<gradient>`](gradient.md) data type, which is a special kind of
[`<image>`](_Resources/Markup%20And%20Styling/css/image.md).

Try it
------

Syntax
------

[css]

```css
/* A conic gradient rotated 45 degrees,
   starting blue and finishing red */
conic-gradient(from 45deg, blue, red);

/* A bluish purple box: the gradient goes from blue to red,
   but only the bottom right quadrant is visible, as the
   center of the conic gradient is at the top left corner */
conic-gradient(from 90deg at 0 0, blue, red);

/* Color wheel */
background: conic-gradient(
    hsl(360, 100%, 50%),
    hsl(315, 100%, 50%),
    hsl(270, 100%, 50%),
    hsl(225, 100%, 50%),
    hsl(180, 100%, 50%),
    hsl(135, 100%, 50%),
    hsl(90, 100%, 50%),
    hsl(45, 100%, 50%),
    hsl(0, 100%, 50%)
);
```

### Values

[`<angle>`](angle.md)

:   Preceded by the `from` keyterm, and taking an angle as its value,
    defines the gradient rotation in clockwise direction.

[`<position>`](#position)

:   Using the same length, order, and keyterm values as the
    [`background-position`](background-position.md) property, the
    `position` value defines center of the gradient. If not specified,
    the value used for `position` by default is `center`, meaning the
    gradient will be centered.

[`<angular-color-stop>`](#angular-color-stop)

:   A color-stop\'s [`<color>`](color_value.md) value, followed by one
    or two optional stop positions, (an [`<angle>`](angle.md) along the
    gradient\'s circumference axis).

[`<color-hint>`](#color-hint)

:   An
    [interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
    hint defining how the gradient progresses between adjacent color
    stops. The length defines at which point between two color stops the
    gradient color should reach the midpoint of the color transition. If
    omitted, the midpoint of the color transition is the midpoint
    between two color stops.

**Note:** Rendering of [color stops in CSS
gradients](#gradient_with_multiple_color_stops) follows the same rules
as color stops in [SVG
gradients](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Gradients).

Description
-----------

As with any gradient, a conic gradient has [](_Resources/Markup%20And%20Styling/css/image.md#description); i.e., it has no natural or preferred
size, nor a preferred ratio. Its concrete size will match the size of
the element it applies to, or the size of the `<image>` if it is set to
something other than the element size.

To create a conic gradient that repeats so as to fill a 360 degree
rotation, use the
[`repeating-conic-gradient()`](repeating-conic-gradient.md) function
instead.

Because `<gradient>`s belong to the `<image>` data type, they can only
be used where `<image>`s can be used. For this reason,
`conic-gradient()` won\'t work on
[`background-color`](background-color.md) and other properties that use
the [`<color>`](color_value.md) data type.

**Note:** Why is it called a \"conic\" gradient? If the color stops are
much lighter on one side than the other, it can look like a cone from
above.

### Composition of a conic gradient

The conic-gradient syntax is similar to the radial-gradient syntax, but
the color-stops are placed around a gradient arc, the circumference of a
circle, rather than on the gradient line emerging from the center of the
gradient. With conic gradients, the colors transition as if spun around
the center of a circle, starting at the top and going clockwise. In a
radial gradient, the colors transition from the center of an ellipse,
outward, in all directions.

A conic gradient is specified by indicating a rotation angle, the center
of the gradient, and then specifying a list of color-stops. Unlike
linear and radial gradients, whose color-stops are placed by specifying
a [length](length.md), the color-stops of a conic gradient are specified
with an [angle](angle.md). Units include `deg` for degrees, `grad` for
gradients, `rad` for radians, and `turn` for turns. There are 360
degrees, 400 gradians, 2π radians, and 1 turn in a circle. Browsers
supporting conic gradients also accept percent values, with 100%
equaling 360 degrees, but this is not in the specification.

Similar to radial gradients, the conic gradient syntax provides for
positioning the center of the gradient anywhere within, or even outside,
the image. The values for the position are similar to the syntax for
2-value background-position.

The gradient arc is the circumference of the gradient. The *starting
point* of the gradient or arc is north, or 12:00pm. The gradient is then
rotated by the *from* angle. The colors of the gradient are determined
by the angled color stops, their starting points, ending points, and, in
between, and optional angled color-stop points. The transitions between
colors can be altered with color hints between adjacent colors\' color
stops.

#### Customizing gradients

By adding more angled color-stop points on the gradient arc, you can
create a highly customized transition between multiple colors. A
color-stop\'s position can be explicitly defined by using an
[`<angle>`](angle.md). If you don\'t specify the location of a color
stop, it is placed halfway between the one that precedes it and the one
that follows it. If you don\'t specify an angle for the first or last
color stop, their values are 0deg and 360deg respectively. The following
two gradients are equivalent:

[css]

```css
conic-gradient(red, orange, yellow, green, blue);
conic-gradient(red 0deg, orange 90deg, yellow 180deg, green 270deg, blue 360deg);
```

By default, colors transition smoothly from the color at one color stop
to the color at the subsequent color stop, with the midpoint between the
colors being the half way point between the color transition. You can
move this color transition midpoint to any point between two color stops
by adding a color hint, indicating where the middle of the color
transition should be. The following is solid red from the start to the
10% mark, transitions from red to blue over 80% of the turn, with the
final 10% being solid blue. The midpoint of the red to blue gradient
change, however, is at the 20% mark rather than the 50% mark as would
have happened without the 80grad, or 20%, color hint.

[css]

```css
conic-gradient(red 40grad, 80grad, blue 360grad);
```

If two or more color stops are at the same location, the transition will
be a hard line between the first and last colors declared at that
location. To use conic gradients to create pie charts --- which is NOT
the correct way to create pie charts as background images are not
accessible --- use hard color stops, where the color stop angles for two
adjacent color stops are the same. The easiest way to do this is to use
multiple position colors stops. The following two declarations are
equivalent:

[css]

```css
conic-gradient(#fff 0.09turn, #bbb 0.09turn, #bbb 0.27turn, #666 0.27turn, #666 0.54turn, #000 0.54turn);
conic-gradient(#fff 0turn 0.09turn, #bbb 0.09turn 0.27turn, #666 0.27turn 0.54turn, #000 0.54turn 1turn);
```

Color stops should be listed in ascending order. Subsequent color stops
of lower value will override the value of the previous color stop
creating a hard transition. The following changes from red to yellow at
the 30% mark, and then transitions from yellow to blue over 35% of the
gradient:

[css]

```css
conic-gradient(red .8rad, yellow .6rad, blue 1.3rad);
```

There are other effects you can create with conic gradients. Oddly, a
checkerboard is one of them. By creating quadrants with an upper left
and lower right white quadrant and lower left and upper right black
quadrants, then repeating the gradient 16 times (four times across and
four times down) you can make a checkerboard.

[css]

```css
conic-gradient(#fff 90deg, #000 0.25turn 0.5turn, #fff 1rad 1.5rad, #000 300grad);
background-size: 25% 25%;
```

And, yes, you can mix and match different angle units, but don\'t. The
above is hard to read.

Formal syntax
-------------

```
<conic-gradient()> = 
  conic-gradient( [ [ from <angle> ]? [ at <position> ]? ]  ||
  <color-interpolation-method> , <angular-color-stop-list> )  

<position> = 
  [ left | center | right ] || [ top | center | bottom ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]?  |
  [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ]  

<color-interpolation-method> = 
  in [ <rectangular-color-space> | <polar-color-space> <hue-interpolation-method>? ]  

<angular-color-stop-list> = 
  <angular-color-stop> , [ <angular-color-hint>? , <angular-color-stop> ]#  

<length-percentage> = 
  <length>      |
  <percentage>  

<rectangular-color-space> = 
  srgb         |
  srgb-linear  |
  lab          |
  oklab        |
  xyz          |
  xyz-d50      |
  xyz-d65      

<polar-color-space> = 
  hsl    |
  hwb    |
  lch    |
  oklch  

<hue-interpolation-method> = 
  [ shorter | longer | increasing | decreasing ] hue  

<angular-color-stop> = 
  <color>              &&
  <color-stop-angle>?  

<angular-color-hint> = 
  <angle-percentage>  

<color-stop-angle> = 
  <angle-percentage>  

<angle-percentage> = 
  <angle>       |
  <percentage>  
```

Accessibility concerns
----------------------

Browsers do not provide any special information on background images to
assistive technology. This is important primarily for screen readers, as
a screen reader will not announce its presence and therefore convey
nothing to its users. While it is possible to create pie charts,
checkerboards, and other effects with conic gradients, CSS images
provide no native way to assign alternative text, and therefore the
image represented by the conic gradient will not be accessible to screen
reader users. If the image contains information critical to
understanding the page\'s overall purpose, it is better to describe it
semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%E2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

Examples
--------

### Gradient at 40-degrees

[css]

```css
div {
  background-image: conic-gradient(from 40deg, #fff, #000);
}
```

### Off-centered gradient

[css]

```css
div {
  background: conic-gradient(from 0deg at 0% 25%, blue, green, yellow 180deg);
}
```

### Gradient pie-chart

This example uses multi-position color stops, with adjacent colors
having the same color stop value, creating a striped effect.

[css]

```css
div {
  background: conic-gradient(red 36deg, orange 36deg 170deg, yellow 170deg);
  border-radius: 50%;
}
```

### Checkerboard

[css]

```css
div {
  background: conic-gradient(
      #fff 0.25turn,
      #000 0.25turn 0.5turn,
      #fff 0.5turn 0.75turn,
      #000 0.75turn
    ) top left / 25% 25% repeat;
  border: 1px solid;
}
```

### More conic-gradient examples

Please see [Using CSS gradients](using_css_gradients.md) for
more examples.

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [CSS Images Module Level 4\
  [\#
  conic-gradients]](https://drafts.csswg.org/css-images-4/#conic-gradients)

  -----------------------------------------------------------------------------------

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

`conic-gradient`

69

79

83

No

56

12.1

69

69

83

48

12.2

10.0

`doubleposition`

72

79

83

No

60

12.1

72

72

83

51

12.2

11.0

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

See also
--------

- [Using CSS gradients](using_css_gradients.md)
- Other gradient functions:
    [`repeating-conic-gradient()`](repeating-conic-gradient.md),
    [`linear-gradient()`](linear-gradient.md),
    [`repeating-linear-gradient()`](repeating-linear-gradient.md),
    [`radial-gradient()`](radial-gradient.md),
    [`repeating-radial-gradient()`](repeating-radial-gradient.md)
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [`image()`](_Resources/Markup%20And%20Styling/css/image/image.md)
- [`element()`](element().md)
- [`image-set()`](image-set.md)
- [`cross-fade()`](cross-fade.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/gradient/conic-gradient>

scale()
=======

The `scale()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) defines a transformation that resizes an
element on the 2D plane. Because the amount of scaling is defined by a
vector \[sx, sy\], it can resize the horizontal and vertical dimensions
at different scales. Its result is a
[`<transform-function>`](transform-function.md) data type.

Try it
------

This scaling transformation is characterized by a two-dimensional
vector. Its coordinates define how much scaling is done in each
direction. If both coordinates are equal, the scaling is uniform
(*isotropic*) and the aspect ratio of the element is preserved (this is
a [homothetic
transformation](https://en.wikipedia.org/wiki/Homothetic_transformation)).

When a coordinate value is outside the \[-1, 1\] range, the element
grows along that dimension; when inside, it shrinks. A negative value
results in a [point
reflection](https://en.wikipedia.org/wiki/Point_reflection) in that
dimension. The value `1` has no effect.

**Note:** The `scale()` function only scales in 2D. To scale in 3D, use
[`scale3d()`](scale3d.md) instead.

Syntax
------

The `scale()` function is specified with either one or two values, which
represent the amount of scaling to be applied in each direction.

[css]

```css
scale(sx)

scale(sx, sy)
```

### Values

[`sx`](#sx)

:   A [`<number>`](number.md) or [`<percentage>`](percentage.md)
    representing the abscissa (horizontal, x-component) of the scaling
    vector.

[`sy`](#sy)

:   A [`<number>`](number.md) or [`<percentage>`](percentage.md)
    representing the ordinate (vertical, y-component) of the scaling
    vector. If not defined, its default value is `sx`, resulting in a
    uniform scaling that preserves the element\'s aspect ratio.

[Cartesian coordinates](transform-function.md#cartesian_coordinates) on
[ℝ\^2](https://en.wikipedia.org/wiki/Real_coordinate_space)

[Homogeneous
coordinates](https://en.wikipedia.org/wiki/Homogeneous_coordinates) on
[ℝℙ\^2](https://en.wikipedia.org/wiki/Real_projective_plane)

Cartesian coordinates on
[ℝ\^3](https://en.wikipedia.org/wiki/Real_coordinate_space)

Homogeneous coordinates on
[ℝℙ\^3](https://en.wikipedia.org/wiki/Real_projective_space)

$\begin
 & 0 \\
0 &  \\
\end$

$\begin
 & 0 & 0 \\
0 &  & 0 \\
0 & 0 & 1 \\
\end$

$\begin
 & 0 & 0 \\
0 &  & 0 \\
0 & 0 & 1 \\
\end$

$\begin
 & 0 & 0 & 0 \\
0 &  & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1 \\
\end$

`[sx 0 0 sy 0 0]`

Accessibility concerns
----------------------

Scaling/zooming animations are problematic for accessibility, as they
are a common trigger for certain types of migraine. If you need to
include such animations on your website, you should provide a control to
allow users to turn off animations, preferably site-wide.

Also, consider making use of the
[`prefers-reduced-motion`](prefers-reduced-motion.md) media
feature --- use it to write a [media query](css_media_queries.md) that
will turn off animations if the user has reduced animation specified in
their system preferences.

Find out more:

- [MDN Understanding WCAG, Guideline 2.3
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.3_%e2%80%94_seizures_and_physical_reactions_do_not_design_content_in_a_way_that_is_known_to_cause_seizures_or_physical_reactions)
- [Understanding Success Criterion 2.3.3 \| W3C Understanding WCAG
    2.1](https://www.w3.org/WAI/WCAG21/Understanding/animation-from-interactions)

Examples
--------

### Scaling the X and Y dimensions together

#### HTML

[html]

```html
<div>Normal</div>
<div class="scaled">Scaled</div>
```

#### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.scaled {
  transform: scale(0.7); /* Equal to scaleX(0.7) scaleY(0.7) */
  background-color: pink;
}
```

#### Result

### Scaling X and Y dimensions separately, and translating the origin

#### HTML

[html]

```html
<div>Normal</div>
<div class="scaled">Scaled</div>
```

#### CSS

[css]

```css
div {
  width: 80px;
  height: 80px;
  background-color: skyblue;
}

.scaled {
  transform: scale(2, 0.5); /* Equal to scaleX(2) scaleY(0.5) */
  transform-origin: left;
  background-color: pink;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  funcdef-transform-scale]](https://drafts.csswg.org/css-transforms/#funcdef-transform-scale)

  -----------------------------------------------------------------------------------------------------

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

1

12

3.5

9

10.5

3.1

2

18

4

11

3.2

1.0

See also
--------

- [`transform`](transform.md)
- [`scale`](_Resources/Markup%20And%20Styling/css/scale.md)
- [`<transform-function>`](transform-function.md)
- [`scale3d()`](scale3d.md)
- Other individual transform properties [`translate`](_Resources/Markup%20And%20Styling/css/translate.md)
    and [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/scale>

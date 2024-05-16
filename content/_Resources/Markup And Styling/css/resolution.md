\<resolution\>
==============

The `<resolution>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md), used for describing [resolutions](_Resources/Markup%20And%20Styling/css/@media/resolution.md)
in [media queries](css_media_queries.md), denotes the pixel density of an
output device, i.e., its resolution.

On screens, the units are related to *CSS* inches, centimeters, or
pixels, not physical values.

Syntax
------

The `<resolution>` data type consists of a strictly positive
[`<number>`](number.md) followed by one of the units listed below. As with
all CSS dimensions, there is no space between the unit literal and the
number.

### Units

[`dpi`](#dpi)

:   Represents the number of [dots per
    inch](https://en.wikipedia.org/wiki/Dots_per_inch). Screens
    typically contains 72 or 96 dots per inch, but the dpi for printed
    documents is usually much greater. As 1 inch is 2.54 cm,
    `1dpi ≈ 0.39dpcm`.

[`dpcm`](#dpcm)

:   Represents the number of [dots per
    centimeter](https://en.wikipedia.org/wiki/Dots_per_inch). As 1 inch
    is 2.54 cm, `1dpcm ≈ 2.54dpi`.

[`dppx`](#dppx)

:   Represents the number of dots per [`px`](length.md#px) unit. Due to the
    1:96 fixed ratio of CSS `in` to CSS `px`, `1dppx` is equivalent to
    `96dpi`, which corresponds to the default resolution of images
    displayed in CSS as defined by
    [`image-resolution`](image-resolution.md).

#### x

:   Alias for `dppx`.

**Note:** Although the number `0` is always the same regardless of unit,
the unit may not be omitted. In other words, `0` is invalid and does not
represent `0dpi`, `0dpcm`, or `0dppx`.

Examples
--------

### Use in a media query

[css]

```css
@media print and (min-resolution: 300dpi) {
  /* … */
}
```

### Valid resolutions

```
96dpi
50.82dpcm
3dppx
```

### Invalid resolutions

```
72 dpi     Spaces are not allowed between the number and the unit.
ten dpi    The number must use digits only.
0          The unit is required.
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  resolution]](https://drafts.csswg.org/css-values/#resolution)

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

`resolution`

29

12

8

3.5Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

9

9.5

No

4.4

29

8

4Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

10.1

No

2.0

`dpcm`

29

12

8

9

1610--15

No

4.4

29

8

1610.1--14

No

2.0

`dpi`

29

12

8

9

1610--15

No

4.4

29

8

1610.1--14

No

2.0

`dppx`

29

12

16

No

12.1

No

4.4

29

16

12.1

No

2.0

`x`

68

79

62

No

55

No

68

68

62

48

No

10.0

See also
--------

- [resolution](_Resources/Markup%20And%20Styling/css/@media/resolution.md) media feature
- The [`image-resolution`](image-resolution.md) property
- [Using \@media queries](using_media_queries.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/resolution>

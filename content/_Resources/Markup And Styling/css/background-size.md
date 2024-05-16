background-size
===============

The `background-size`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the size of the element\'s background image. The image can be left to
its natural size, stretched, or constrained to fit the available space.

Try it
------

Spaces not covered by a background image are filled with the
[`background-color`](background-color.md) property, and the background
color will be visible behind background images that have
transparency/translucency.

Syntax
------

[css]

```css
/* Keyword values */
background-size: cover;
background-size: contain;

/* One-value syntax */
/* the width of the image (height becomes 'auto') */
background-size: 50%;
background-size: 3.2em;
background-size: 12px;
background-size: auto;

/* Two-value syntax */
/* first value: width of the image, second value: height */
background-size: 50% auto;
background-size: 3em 25%;
background-size: auto 6px;
background-size: auto auto;

/* Multiple backgrounds */
background-size: auto, auto; /* Not to be confused with `auto auto` */
background-size: 50%, 25%, 25%;
background-size: 6px, auto, contain;

/* Global values */
background-size: inherit;
background-size: initial;
background-size: revert;
background-size: revert-layer;
background-size: unset;
```

The `background-size` property is specified in one of the following
ways:

- Using the keyword values `contain` or `cover`.
- Using a width value only, in which case the height defaults to
    `auto`.
- Using both a width and a height value, in which case the first sets
    the width and the second sets the height. Each value can be a
    [`<length>`](length.md), a [`<percentage>`](percentage.md), or `auto`.

To specify the size of multiple background images, separate the value
for each one with a comma.

### Values

[`contain`](#contain)

:   Scales the image as large as possible within its container without
    cropping or stretching the image. If the container is larger than
    the image, this will result in image tiling, unless the
    [`background-repeat`](background-repeat.md) property is set to
    `no-repeat`.

[`cover`](#cover)

:   Scales the image (while preserving its ratio) to the smallest
    possible size to fill the container (that is: both its height and
    width completely *cover* the container), leaving no empty space. If
    the proportions of the background differ from the element, the image
    is cropped either vertically or horizontally.

[`auto`](#auto)

:   Scales the background image in the corresponding direction such that
    its intrinsic proportions are maintained.

[`<length>`](length.md)

:   Stretches the image in the corresponding dimension to the specified
    length. Negative values are not allowed.

[`<percentage>`](percentage.md)

:   Stretches the image in the corresponding dimension to the specified
    percentage of the *background positioning area*. The background
    positioning area is determined by the value of
    [`background-origin`](background-origin.md) (by default, the padding
    box). However, if the background\'s
    [`background-attachment`](background-attachment.md) value is `fixed`,
    the positioning area is instead the entire
    [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).
    Negative values are not allowed.

### Intrinsic dimensions and proportions

The computation of values depends on the image\'s intrinsic dimensions
(width and height) and intrinsic proportions (width-to-height ratio).
These attributes are as follows:

- A bitmap image (such as JPG) always has intrinsic dimensions and
    proportions.
- A vector image (such as SVG) does not necessarily have intrinsic
    dimensions. If it has both horizontal and vertical intrinsic
    dimensions, it also has intrinsic proportions. If it has no
    dimensions or only one dimension, it may or may not have
    proportions.
- CSS [`<gradient>`](gradient.md)s have no intrinsic dimensions or
    intrinsic proportions.
- Background images created with the [`element()`](element().md) function
    use the intrinsic dimensions and proportions of the generating
    element.

**Note:** In Gecko, background images created using the
[`element()`](element().md) function are currently treated as images with
the dimensions of the element, or of the background positioning area if
the element is SVG, with the corresponding intrinsic proportion. This is
non-standard behavior.

Based on the intrinsic dimensions and proportions, the rendered size of
the background image is computed as follows:

- **If both components of `background-size` are specified and are not
    `auto`:** The background image is rendered at the specified size.
- **If the `background-size` is `contain` or `cover`:** While
    preserving its intrinsic proportions, the image is rendered at the
    largest size contained within, or covering, the background
    positioning area. If the image has no intrinsic proportions, then
    it\'s rendered at the size of the background positioning area.
- **If the `background-size` is `auto` or `auto auto`:**
  - If the image has both horizontal and vertical intrinsic
        dimensions, it\'s rendered at that size.
  - If the image has no intrinsic dimensions and has no intrinsic
        proportions, it\'s rendered at the size of the background
        positioning area.
  - If the image has no intrinsic dimensions but has intrinsic
        proportions, it\'s rendered as if `contain` had been specified
        instead.
  - If the image has only one intrinsic dimension and has intrinsic
        proportions, it\'s rendered at the size corresponding to that
        one dimension. The other dimension is computed using the
        specified dimension and the intrinsic proportions.
  - If the image has only one intrinsic dimension but has no
        intrinsic proportions, it\'s rendered using the specified
        dimension and the other dimension of the background positioning
        area.

    **Note:** SVG images have a
    [`preserveAspectRatio`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/preserveAspectRatio)
    attribute that defaults to the equivalent of `contain`; an explicit
    `background-size` causes `preserveAspectRatio` to be ignored.

- **If the `background-size` has one `auto` component and one
    non-`auto` component:**
  - If the image has intrinsic proportions, it\'s stretched to the
        specified dimension. The unspecified dimension is computed using
        the specified dimension and the intrinsic proportions.
  - If the image has no intrinsic proportions, it\'s stretched to
        the specified dimension. The unspecified dimension is computed
        using the image\'s corresponding intrinsic dimension, if there
        is one. If there is no such intrinsic dimension, it becomes the
        corresponding dimension of the background positioning area.

**Note:** Background sizing for vector images that lack intrinsic
dimensions or proportions is not yet fully implemented in all browsers.
Be careful about relying on the behavior described above, and test in
multiple browsers to be sure the results are acceptable.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto auto`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  Percentages                        relative to the background positioning area
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     a repeatable list
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-size = 
  <bg-size>#  

<bg-size> = 
  [ <length-percentage [0,∞]> | auto ]  |
  cover                                      |
  contain                                    

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Tiling a large image

Let\'s consider a large image, a 2982x2808 Firefox logo image. We want
to tile four copies of this image into a 300x300-pixel element. To do
this, we can use a fixed `background-size` value of 150 pixels.

#### HTML

[html]

```html
<div class="tiledBackground"></div>
```

#### CSS

[css]

```css
.tiledBackground {
  background-image: url(https://www.mozilla.org/media/img/logos/firefox/logo-quantum.9c5e96634f92.png);
  background-size: 150px;
  width: 300px;
  height: 300px;
  border: 2px solid;
  color: pink;
}
```

#### Result

See [](resizing_background_images.md) for more
examples.

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-background-size]](https://drafts.csswg.org/css-backgrounds/#the-background-size)

  ----------------------------------------------------------------------------------------------

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

`background-size`

3

1WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

1212

4943.6--4

9

15WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

10

9.5--15Opera 9.5\'s computation of the background positioning area is
incorrect for fixed backgrounds. Opera 9.5 also interprets the two-value
form as a horizontal scaling factor and, from appearances, a vertical
clipping dimension. This has been fixed in Opera 10.

5

3WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

≤37WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

2.2

18

18WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

494

14WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

10.1

10.1--14Opera 9.5\'s computation of the background positioning area is
incorrect for fixed backgrounds. Opera 9.5 also interprets the two-value
form as a horizontal scaling factor and, from appearances, a vertical
clipping dimension. This has been fixed in Opera 10.

4.2

1WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

1.0

1.0WebKit-based browsers originally implemented an older draft of CSS3
`background-size` in which an omitted second value is treated as
duplicating the first value; this draft does not include the `contain`
or `cover` keywords.

`contain_and_cover`

3

12

3.6

9

10

5

37

18

4

14

4.2

1.0

See also
--------

- [](resizing_background_images.md)
- [Scaling of SVG backgrounds](scaling_of_svg_backgrounds.md)
- [`object-fit`](object-fit.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-size>

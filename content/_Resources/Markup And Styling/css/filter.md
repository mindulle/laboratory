filter
======

The `filter` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property applies graphical effects like blur or color shift to an
element. Filters are commonly used to adjust the rendering of images,
backgrounds, and borders.

Several [functions](#functions), such as `blur()` and `contrast()`, are
available to help you achieve predefined effects.

Try it
------

Syntax
------

[css]

```css
/* <filter-function> values */
filter: blur(5px);
filter: brightness(0.4);
filter: contrast(200%);
filter: drop-shadow(16px 16px 20px blue);
filter: grayscale(50%);
filter: hue-rotate(90deg);
filter: invert(75%);
filter: opacity(25%);
filter: saturate(30%);
filter: sepia(60%);

/* URL */
filter: url("filters.svg#filter-id");

/* Multiple filters */
filter: contrast(175%) brightness(3%);
filter: drop-shadow(3px 3px red) sepia(100%) drop-shadow(-3px -3px blue);

/* Use no filter */
filter: none;

/* Global values */
filter: inherit;
filter: initial;
filter: revert;
filter: revert-layer;
filter: unset;
```

With a function, use the following:

[css]

```css
filter: <filter-function> [<filter-function>]* | none;
```

You can use `url()` to reference an [SVG filter
element](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter).
For a reference to an SVG
[`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)
element, use the following syntax:

[css]

```css
filter: url(file.svg#filter-element-id);
```

Functions
---------

The `filter` property is specified as `none` or one or more of the
functions listed below. If the parameter for any function is invalid,
the function returns `none`. Except where noted, the functions that take
a value expressed with a percent sign (as in `34%`) also accept the
value expressed as decimal (as in `0.34`).

When the `filter` property values contains multiple functions, the
filters are applied in order.

[`blur()`](blur.md)

:   Applies a Gaussian blur to the input image.

    [css]

    ```css
    filter: blur(5px);
    ```

[`brightness()`](brightness.md)

:   Applies a linear multiplier to the input image, making it appear
    more or less bright. Values are linear multipliers on the effect,
    with `0%` creating a completely black image, `100%` having no
    effect, and values over `100%` brightening the image.

    [css]

    ```css
    filter: brightness(2);
    ```

[`contrast()`](contrast.md)

:   Adjusts the contrast of the input image. A value of `0%` makes the
    image grey, `100%` has no effect, and values over `100%` create a
    contrast.

    [css]

    ```css
    filter: contrast(200%);
    ```

[`drop-shadow()`](drop-shadow.md)

:   Applies the parameter `<shadow>` as a drop shadow, following the
    contours of the image. The shadow syntax is similar to
    `<box-shadow>` (defined in the [](css_backgrounds_and_borders.md)), with the exception that the
    `inset` keyword and `spread` parameter are not allowed. As with all
    `filter` property values, any filters after the `drop-shadow()` are
    applied to the shadow.

    [css]

    ```css
    filter: drop-shadow(16px 16px 10px black);
    ```

[`grayscale()`](grayscale.md)

:   Converts the image to grayscale. A value of `100%` is completely
    grayscale. The initial value of `0%` leaves the input unchanged.
    Values between `0%` and `100%` produce linear multipliers on the
    effect.

    [css]

    ```css
    filter: grayscale(100%);
    ```

[`hue-rotate()`](hue-rotate.md)

:   Applies a hue rotation. The `<angle>` value defines the number of
    degrees around the hue color circle at which the input samples will
    be adjusted. A value of `0deg` leaves the input unchanged.

    [css]

    ```css
    filter: hue-rotate(90deg);
    ```

[`invert()`](invert.md)

:   Inverts the samples in the input image. A value of `100%` completely
    inverts the image. A value of `0%` leaves the input unchanged.
    Values between `0%` and `100%` have linear multipliers on the
    effect.

    [css]

    ```css
    filter: invert(100%);
    ```

[`opacity()`](_Resources/Markup%20And%20Styling/css/filter-function/opacity.md)

:   Applies transparency. `0%` makes the image completely transparent
    and `100%` leaves the image unchanged.

    [css]

    ```css
    filter: opacity(50%);
    ```

[`saturate()`](saturate.md)

:   Saturates the image, with `0%` being completely unsaturated, `100%`
    leaving the image unchanged, and values of over `100%` increasing
    saturation.

    [css]

    ```css
    filter: saturate(200%);
    ```

[`sepia()`](sepia.md)

:   Converts the image to sepia, with a value of `100%` making the image
    completely sepia and `0%` making no change.

    [css]

    ```css
    filter: sepia(100%);
    ```

Combining functions
-------------------

You may combine any number of functions to manipulate the rendering. The
filters are applied in the order declared. The following example
enhances the contrast and brightness of the image:

[css]

```css
filter: contrast(175%) brightness(103%);
```

### Interpolation

When animated, if both the beginning and end filters have a function
list of the same length without [`url()`](url.md) in the same order, each
of their filter functions is
[interpolated](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
according to the filter function\'s specific rules.

If the filter lists are of different lengths, the missing equivalent
filter functions from the longer list are added to the end of the
shorter list. The added functions use their initial, no filter
modification values. All the filters listed are then interpolated
according to the filter function\'s specific rules. Otherwise, discrete
interpolation is used.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     a [filter function list](filter.md#interpolation)
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
filter = 
  none                 |
  <filter-value-list>  

<filter-value-list> = 
  [ <filter-function> | <url> ]+  

<filter-function> = 
  <blur()>         |
  <brightness()>   |
  <contrast()>     |
  <drop-shadow()>  |
  <grayscale()>    |
  <hue-rotate()>   |
  <invert()>       |
  <opacity()>      |
  <sepia()>        |
  <saturate()>     

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Applying filter functions

The `filter` property is applied to the second image, greying and
blurring both the image and its border.

[css]

```css
img {
  border: 5px solid yellow;
}
/* Gray the second image by 40% and blur by 5px */
img:nth-of-type(2) {
  filter: grayscale(0.4) blur(5px);
}
```

[html]

```html
<img src="pencil.jpg" alt="Original image is sharp" />
<img src="pencil.jpg" alt="The image and border are blurred and muted" />
```

### Repeating filter functions

Filter functions are applied in order of appearance. The same filter
function can be repeated.

[css]

```css
#MDN-logo {
  border: 1px solid blue;
  filter: drop-shadow(5px 5px 0 red) hue-rotate(180deg) drop-shadow(5px 5px 0
        red);
}
```

The filters are applied in order. This is why the drop shadows are not
the same color: the first drop shadow\'s hue is altered by the
`hue-rotate()` function but the second one is not.

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [Filter Effects Module Level 1\
  [\#
  FilterProperty]](https://drafts.fxtf.org/filter-effects/#FilterProperty)

  ----------------------------------------------------------------------------------

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

`filter`

53

18In Chrome 18 to 19, the `saturate()` function only takes integers
instead of decimal or percentage values. From Chrome 20, this bug is
fixed.

1212

4935

NoInternet Explorer 4 to 9 implemented a non-standard `filter` property.
The syntax was completely different from this one and is not documented
here.

4015

9.16

534.4

53

4935

4114

9.36

6.0

`svg`

No

No

35

No

No

No

No

No

35

No

No

No

See also
--------

- CSS [`backdrop-filter`](backdrop-filter.md) property
- CSS [compositing and blending](css_compositing_and_blending.md) module,
    including the CSS [`background-blend-mode`](background-blend-mode.md)
    and [`mix-blend-mode`](mix-blend-mode.md) properties.
- The CSS [`mask`](mask.md) property
- [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG), including
    the SVG
    [`<filter>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/filter)
    element and SVG `filter` attribute.
- [Applying SVG effects to HTML
    content](https://developer.mozilla.org/en-US/docs/Web/SVG/Applying_SVG_effects_to_HTML_content)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/filter>

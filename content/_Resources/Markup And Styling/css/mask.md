mask
====

The `mask` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[shorthand property](shorthand_properties.md) hides an element (partially
or fully) by masking or clipping the image at specific points.

**Note:** As well as the properties listed below, the `mask` shorthand
also resets [`mask-border`](mask-border.md) to its initial value. It is
therefore recommended to use the `mask` shorthand rather than other
shorthands or the individual properties to override any mask settings
earlier in the cascade. This will ensure that `mask-border` has also
been reset to allow the new styles to take effect.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`mask-clip`](mask-clip.md)
- [`mask-composite`](mask-composite.md)
- [`mask-image`](mask-image.md)
- [`mask-mode`](mask-mode.md)
- [`mask-origin`](mask-origin.md)
- [`mask-position`](mask-position.md)
- [`mask-repeat`](mask-repeat.md)
- [`mask-size`](mask-size.md)

Syntax
------

[css]

```css
/* Keyword values */
mask: none;

/* Image values */
mask: url(mask.png); /* Pixel image used as mask */
mask: url(masks.svg#star); /* Element within SVG graphic used as mask */

/* Combined values */
mask: url(masks.svg#star) luminance; /* Element within SVG graphic used as luminance mask */
mask: url(masks.svg#star) 40px 20px; /* Element within SVG graphic used as mask positioned 40px from the top and 20px from the left */
mask: url(masks.svg#star) 0 0/50px 50px; /* Element within SVG graphic used as mask with a width and height of 50px */
mask: url(masks.svg#star) repeat-x; /* Element within SVG graphic used as horizontally repeated mask */
mask: url(masks.svg#star) stroke-box; /* Element within SVG graphic used as mask extending to the box enclosed by the stroke */
mask: url(masks.svg#star) exclude; /* Element within SVG graphic used as mask and combined with background using non-overlapping parts */

/* Global values */
mask: inherit;
mask: initial;
mask: revert;
mask: revert-layer;
mask: unset;

/* Multiple masks */
mask:
  url(masks.svg#star) left / 16px repeat-y,
  /* Element within SVG graphic is used as a mask on the left-hand side with a width of 16px */
    url(masks.svg#circle) right / 16px repeat-y; /* Element within SVG graphic is used as a mask on the right-hand side with a width of 16px */
```

### Values

[`<mask-reference>`](#mask-reference)

:   Sets the mask image source. See [`mask-image`](mask-image.md).

[`<masking-mode>`](#masking-mode)

:   Sets the masking mode of the mask image. See
    [`mask-mode`](mask-mode.md).

[`<position>`](#position)

:   Sets the position of the mask image. See
    [`mask-position`](mask-position.md).

[`<bg-size>`](#bg-size)

:   Sets the size of the mask image. See [`mask-size`](mask-size.md).

[`<repeat-style>`](#repeat-style)

:   Sets the repetition of the mask image. See
    [`mask-repeat`](mask-repeat.md).

[`<geometry-box>`](#geometry-box)

:   If only one `<geometry-box>` value is given, it sets both
    [`mask-origin`](mask-origin.md) and [`mask-clip`](mask-clip.md). If two
    `<geometry-box>` values are present, then the first sets
    [`mask-origin`](mask-origin.md) and the second sets
    [`mask-clip`](mask-clip.md).

[`<geometry-box> | no-clip`](#geometry-box_no-clip)

:   Sets the area that is affected by the mask image. See
    [`mask-clip`](mask-clip.md).

[`<compositing-operator>`](#compositing-operator)

:   Sets the compositing operation used on the current mask layer. See
    [`mask-composite`](mask-composite.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`mask-image`](mask-image.md):   |
|                                   |     `none`                        |
|                                   | -   [`mask-mode`](mask-mode.md):     |
|                                   |     `match-source`                |
|                                   | -   [`mask-repeat`](mask-repeat.md): |
|                                   |     `repeat`                      |
|                                   | -                                 |
|                                   | [`mask-position`](mask-position.md): |
|                                   |     `center`                      |
|                                   | -   [`mask-clip`](mask-clip.md):     |
|                                   |     `border-box`                  |
|                                   | -   [`mask-origin`](mask-origin.md): |
|                                   |     `border-box`                  |
|                                   | -   [`mask-size`](mask-size.md):     |
|                                   |     `auto`                        |
|                                   | -   [](mask-composite.md): |
|                                   |     `add`                         |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements; In SVG, it applies  |
|                                   | to container elements excluding   |
|                                   | the                               |
|                                   | [`<defs                           |
|                                   | >`](https://developer.mozilla.org |
|                                   | /en-US/docs/Web/SVG/Element/defs) |
|                                   | element and all graphics elements |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`mask-position`](mask-position.md): |
|                                   |     refer to size of mask         |
|                                   |     painting area minus size of   |
|                                   |     mask layer image (see the     |
|                                   |     text for                      |
|                                   |     [](background-position.md)) |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`mask-image`](mask-image.md):   |
|                                   |     as specified, but with        |
|                                   |     [`url()`](url.md) values made    |
|                                   |     absolute                      |
|                                   | -   [`mask-mode`](mask-mode.md): as  |
|                                   |     specified                     |
|                                   | -   [`mask-repeat`](mask-repeat.md): |
|                                   |     Consists of two keywords, one |
|                                   |     per dimension                 |
|                                   | -                                 |
|                                   | [`mask-position`](mask-position.md): |
|                                   |     Consists of two keywords      |
|                                   |     representing the origin and   |
|                                   |     two offsets from that origin, |
|                                   |     each given as an absolute     |
|                                   |     length (if given a            |
|                                   |     \<length\>), otherwise as a   |
|                                   |     percentage.                   |
|                                   | -   [`mask-clip`](mask-clip.md): as  |
|                                   |     specified                     |
|                                   | -   [`mask-origin`](mask-origin.md): |
|                                   |     as specified                  |
|                                   | -   [`mask-size`](mask-size.md): as  |
|                                   |     specified, but with relative  |
|                                   |     lengths converted into        |
|                                   |     absolute lengths              |
|                                   | -   [](mask-composite.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`mask-image`](mask-image.md):   |
|                                   |     discrete                      |
|                                   | -   [`mask-mode`](mask-mode.md):     |
|                                   |     discrete                      |
|                                   | -   [`mask-repeat`](mask-repeat.md): |
|                                   |     discrete                      |
|                                   | -                                 |
|                                   | [`mask-position`](mask-position.md): |
|                                   |     a repeatable list             |
|                                   | -   [`mask-clip`](mask-clip.md):     |
|                                   |     discrete                      |
|                                   | -   [`mask-origin`](mask-origin.md): |
|                                   |     discrete                      |
|                                   | -   [`mask-size`](mask-size.md): a   |
|                                   |     repeatable list               |
|                                   | -   [](mask-composite.md): |
|                                   |     discrete                      |
+-----------------------------------+-----------------------------------+
| Creates [stacking                 | yes                               |
| cont                              |                                   |
| ext](css_positioned_layout/unders |                                   |
| tanding_z-index/stacking_context) |                                   |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
mask = 
  <mask-layer>#  

<mask-layer> = 
  <mask-reference>              ||
  <position> [ / <bg-size> ]?   ||
  <repeat-style>                ||
  <geometry-box>                ||
  [ <geometry-box> | no-clip ]  ||
  <compositing-operator>        ||
  <masking-mode>                

<mask-reference> = 
  none           |
  <image>        |
  <mask-source>  

<position> = 
  [ left | center | right ] || [ top | center | bottom ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]?  |
  [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ]  

<bg-size> = 
  [ <length-percentage [0,∞]> | auto ]  |
  cover                                      |
  contain                                    

<repeat-style> = 
  repeat-x                                     |
  repeat-y                                     |
  [ repeat | space | round | no-repeat ]  

<geometry-box> = 
  <shape-box>  |
  fill-box     |
  stroke-box   |
  view-box     

<compositing-operator> = 
  add        |
  subtract   |
  intersect  |
  exclude    

<masking-mode> = 
  alpha         |
  luminance     |
  match-source  

<image> = 
  <url>       |
  <gradient>  

<mask-source> = 
  <url>  

<length-percentage> = 
  <length>      |
  <percentage>  

<shape-box> = 
  <box>       |
  margin-box  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  

<box> = 
  border-box   |
  padding-box  |
  content-box  
```

Examples
--------

### Masking an image

[css]

```css
.target {
  mask: url(#c1) luminance;
}

.anothertarget {
  mask: url(resources.svg#c1) 50px 30px/10px 10px repeat-x exclude;
}
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\# the-mask]](https://drafts.fxtf.org/css-masking/#the-mask)

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

`mask`

1While the property is recognized, values applied to it don\'t have any
effect.

1The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

79While the property is recognized, values applied to it don\'t have any
effect.

79The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

12--79

2From Firefox 10, the default color space when handling masks is sRGB.
Previously, the default and only supported color space was linear RGB.
This changes the appearance of mask effects, but brings Firefox into
compliance with the second edition of the SVG 1.1 specification.

No

15While the property is recognized, values applied to it don\'t have any
effect.

15The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

3.1While the property is recognized, values applied to it don\'t have
any effect.

3.1The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

2While the property is recognized, values applied to it don\'t have any
effect.

2The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

18While the property is recognized, values applied to it don\'t have any
effect.

18The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

4From Firefox 10, the default color space when handling masks is sRGB.
Previously, the default and only supported color space was linear RGB.
This changes the appearance of mask effects, but brings Firefox into
compliance with the second edition of the SVG 1.1 specification.

14While the property is recognized, values applied to it don\'t have any
effect.

14The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

2While the property is recognized, values applied to it don\'t have any
effect.

2The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

1.0While the property is recognized, values applied to it don\'t have
any effect.

1.0The prefixed property can be used with SVG and HTML with a slightly
different syntax, which allows setting the non-standard
[`-webkit-mask-attachment`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-attachment)
property.

See also
--------

- [`clip-path`](clip-path.md), [`filter`](filter.md)
- [CSS Shapes, clipping and masking -- and how to use
    them](https://hacks.mozilla.org/2017/06/css-shapes-clipping-and-masking/)
- [Applying SVG effects to HTML
    content](https://developer.mozilla.org/en-US/docs/Web/SVG/Applying_SVG_effects_to_HTML_content)
- [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask>

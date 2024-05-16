mask-image
==========

The `mask-image` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the image that is used as mask layer for an element. By
default this means the alpha channel of the mask image will be
multiplied with the alpha channel of the element. This can be controlled
with the [`mask-mode`](mask-mode.md) property.

Syntax
------

[css]

```css
/* Keyword value */
mask-image: none;

/* <mask-source> value */
mask-image: url(masks.svg#mask1);

/* <image> values */
mask-image: linear-gradient(rgba(0, 0, 0, 1), transparent);
mask-image: image(url(mask.png), skyblue);

/* Multiple values */
mask-image: image(url(mask.png), skyblue), linear-gradient(rgba(0, 0, 0, 1), transparent);

/* Global values */
mask-image: inherit;
mask-image: initial;
mask-image: revert;
mask-image: revert-layer;
mask-image: unset;
```

### Values

[`none`](#none)

:   This keyword is interpreted as an opaque white image layer.

[`<mask-source>`](#mask-source)

:   A [`url()`](url.md) reference to a
    [`<mask>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask)
    or to a CSS image.

[`<image>`](_Resources/Markup%20And%20Styling/css/image.md)

:   An image value used as mask image layer.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, but with [`url()`](url.md) values made absolute
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-image = 
  <mask-reference>#  

<mask-reference> = 
  none           |
  <image>        |
  <mask-source>  

<image> = 
  <url>       |
  <gradient>  

<mask-source> = 
  <url>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Setting a mask image with a URL

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-image]](https://drafts.fxtf.org/css-masking/#the-mask-image)

  -------------------------------------------------------------------------------

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

`mask-image`

1From version 8, Chrome added support for gradient values. Initially,
Chrome supported only `-webkit-` prefixed values for gradients (such as
`-webkit-linear-gradient()`). Later, support for unprefixed values was
added.

7916--79

53

No

15

15.4

4Initially, Safari supported only `-webkit-` prefixed values for
gradients (such as `-webkit-linear-gradient()`). Later, support for
unprefixed values was added.

2Initially, Android supported only `-webkit-` prefixed values for
gradients (such as `-webkit-linear-gradient()`). Later, support for
unprefixed values was added.

18From version 8, Chrome added support for gradient values. Initially,
Chrome supported only `-webkit-` prefixed values for gradients (such as
`-webkit-linear-gradient()`). Later, support for unprefixed values was
added.

53

14

15.4

3.2Initially, Safari supported only `-webkit-` prefixed values for
gradients (such as `-webkit-linear-gradient()`). Later, support for
unprefixed values was added.

1.0

`multiple_mask_images`

1

18

53

No

15

4

≤37

18

53

14

3.2

1.0

`svg_masks`

8

18

53

No

15

4

≤37

18

53

14

3.2

1.0

See also
--------

- [Clipping and Masking in
    CSS](https://css-tricks.com/clipping-masking-css/)
- [Apply effects to images with CSS\'s mask-image
    property](https://web.dev/css-masking/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-image>

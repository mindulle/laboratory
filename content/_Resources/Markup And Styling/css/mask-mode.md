mask-mode
=========

The `mask-mode` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether the mask reference defined by
[`mask-image`](mask-image.md) is treated as a luminance or alpha mask.

Syntax
------

[css]

```css
/* Keyword values */
mask-mode: alpha;
mask-mode: luminance;
mask-mode: match-source;

/* Multiple values */
mask-mode: alpha, match-source;

/* Global values */
mask-mode: inherit;
mask-mode: initial;
mask-mode: revert;
mask-mode: revert-layer;
mask-mode: unset;
```

The `mask-mode` property is specified as one or more of the keyword
values listed below, separated by commas.

### Values

[`alpha`](#alpha)

:   This keyword indicates that the transparency (alpha channel) values
    of the mask layer image should be used as the mask values.

[`luminance`](#luminance)

:   This keyword indicates that the luminance values of the mask layer
    image should be used as the mask values.

[`match-source`](#match-source)

:   If the [`mask-image`](mask-image.md) property is of type
    `<mask-source>`, the luminance values of the mask layer image should
    be used as the mask values.

    If it is of type [`<image>`](image), the alpha values of the mask
    layer image should be used as the mask values.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `match-source`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-mode = 
  <masking-mode>#  

<masking-mode> = 
  alpha         |
  luminance     |
  match-source  
```

Examples
--------

### Using alpha mask mode

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-mode]](https://drafts.fxtf.org/css-masking/#the-mask-mode)

  -----------------------------------------------------------------------------

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

`mask-mode`

No

No

53

No

No

15.4

No

No

53

No

15.4

No

See also
--------

- [Clipping and Masking in
    CSS](https://css-tricks.com/clipping-masking-css/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-mode>

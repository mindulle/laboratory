mask-border-mode
================

The `mask-border-mode`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the blending mode used in a [mask border](mask-border.md).

Syntax
------

[css]

```css
/* Keyword values */
mask-border-mode: luminance;
mask-border-mode: alpha;

/* Global values */
mask-border-mode: inherit;
mask-border-mode: initial;
mask-border-mode: revert;
mask-border-mode: revert-layer;
mask-border-mode: unset;
```

### Values

[`luminance`](#luminance)

:   The luminance values of the mask border image are used as the mask
    values.

[`alpha`](#alpha)

:   The alpha values of the mask border image are used as the mask
    values.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `alpha`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-border-mode = 
  luminance  |
  alpha      
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-border-mode]](https://drafts.fxtf.org/css-masking-1/#the-mask-border-mode)

  ---------------------------------------------------------------------------------------------

Browser compatibility
---------------------

See also
--------

- [`mask-border`](mask-border.md)
- [`mask-border-outset`](mask-border-outset.md)
- [`mask-border-repeat`](mask-border-repeat.md)
- [`mask-border-source`](mask-border-source.md)
- [`mask-border-width`](mask-border-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-mode>

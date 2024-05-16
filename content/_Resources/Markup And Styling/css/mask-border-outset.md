mask-border-outset
==================

The `mask-border-outset`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the distance by which an element\'s [mask border](mask-border.md)
is set out from its border box.

Syntax
------

[css]

```css
/* <length> value */
mask-border-outset: 1rem;

/* <number> value */
mask-border-outset: 1.5;

/* top and bottom | left and right */
mask-border-outset: 1 1.2;

/* top | left and right | bottom */
mask-border-outset: 30px 2 45px;

/* top | right | bottom | left */
mask-border-outset: 7px 12px 14px 5px;

/* Global values */
mask-border-outset: inherit;
mask-border-outset: initial;
mask-border-outset: revert;
mask-border-outset: revert-layer;
mask-border-outset: unset;
```

The `mask-border-outset` property may be specified as one, two, three,
or four values. Each value is a [`<length>`](length.md) or
[`<number>`](number.md). Negative values are invalid.

- When **one** value is specified, it applies the same outset to **all
    four sides**.
- When **two** values are specified, the first outset applies to the
    **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first outset applies to the
    **top**, the second to the **left and right**, the third to the
    **bottom**.
- When **four** values are specified, the outsets apply to the
    **top**, **right**, **bottom**, and **left** in that order
    (clockwise).

### Values

[`<length>`](length.md)

:   The size of the mask border outset as a dimension.

[`<number>`](number.md)

:   The size of the mask border outset as a multiple of the
    corresponding [`border-width`](border-width.md).

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-border-outset = 
  [ <length> | <number> ]  
```

Examples
--------

### Basic usage

This property doesn\'t appear to be supported anywhere yet. When it
eventually starts to be supported, it will serve to move the mask away
from the inner edge of the element\'s border box --- you can use it to
make the mask start from part way across the border, rather than the
inside of it.

[css]

```css
mask-border-outset: 1rem;
```

Chromium-based browsers support an outdated version of this property ---
`mask-box-image-outset` --- with a prefix:

[css]

```css
-webkit-mask-box-image-outset: 1rem;
```

**Note:** The [`mask-border`](mask-border.md) page features a working
example (using the out-of-date prefixed border mask properties supported
in Chromium), so you can get an idea of the effect.

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-border-outset]](https://drafts.fxtf.org/css-masking/#the-mask-border-outset)

  -----------------------------------------------------------------------------------------------

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

`mask-border-outset`

1

79

No

No

15

3.1

4.4

18

No

14

3

1.0

See also
--------

- [`mask-border`](mask-border.md)
- [`mask-border-mode`](mask-border-mode.md)
- [`mask-border-repeat`](mask-border-repeat.md)
- [`mask-border-source`](mask-border-source.md)
- [`mask-border-width`](mask-border-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-outset>

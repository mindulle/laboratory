mask-border-repeat
==================

The `mask-border-repeat`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how the [edge regions](border-image-slice.md#edge-regions) of a source
image are adjusted to fit the dimensions of an element\'s [](mask-border.md).

Syntax
------

[css]

```css
/* Keyword value */
mask-border-repeat: stretch;
mask-border-repeat: repeat;
mask-border-repeat: round;
mask-border-repeat: space;

/* top and bottom | left and right */
mask-border-repeat: round stretch;

/* Global values */
mask-border-repeat: inherit;
mask-border-repeat: initial;
mask-border-repeat: revert;
mask-border-repeat: revert-layer;
mask-border-repeat: unset;
```

The `mask-border-repeat` property may be specified using one or two
values chosen from the list of values below.

- When **one** value is specified, it applies the same behavior on
    **all four sides**.
- When **two** values are specified, the first applies to the **top
    and bottom**, the second to the **left and right**.

### Values

[`stretch`](#stretch)

:   The source image\'s edge regions are stretched to fill the gap
    between each border.

[`repeat`](#repeat)

:   The source image\'s edge regions are tiled (repeated) to fill the
    gap between each border. Tiles may be clipped to achieve the proper
    fit.

[`round`](#round)

:   The source image\'s edge regions are tiled (repeated) to fill the
    gap between each border. Tiles may be stretched to achieve the
    proper fit.

[`space`](#space)

:   The source image\'s edge regions are tiled (repeated) to fill the
    gap between each border. Extra space will be distributed in between
    tiles to achieve the proper fit.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `stretch`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-border-repeat = 
  [ stretch | repeat | round | space ]  
```

Examples
--------

### Basic usage

This property doesn\'t appear to be supported anywhere yet. When it
eventually starts to be supported, it will serve to define how the
border mask slice will repeat around the border --- i.e. will it just
repeat, or be scaled slightly so a whole number of slices fits, or be
stretched so one slice fits?

[css]

```css
mask-border-repeat: round;
```

Chromium-based browsers support an outdated version of this property ---
`mask-box-image-repeat` --- with a prefix:

[css]

```css
-webkit-mask-box-image-repeat: round;
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
  the-mask-border-repeat]](https://drafts.fxtf.org/css-masking/#the-mask-border-repeat)

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

`mask-border-repeat`

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
- [`mask-border-outset`](mask-border-outset.md)
- [`mask-border-source`](mask-border-source.md)
- [`mask-border-width`](mask-border-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-border-repeat>

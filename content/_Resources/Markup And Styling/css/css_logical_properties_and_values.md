CSS logical properties and values
=================================

The **CSS logical properties and values** module introduces logical
properties and values that provide the ability to control layout through
logical, rather than physical, direction and dimension mappings.

The module also defines logical properties and values for properties
previously defined in CSS 2.1. Logical properties define
direction‐relative equivalents of their corresponding physical
properties.

### Block vs. inline

Logical properties and values use the abstract terms *block* and
*inline* to describe the direction in which they flow. The physical
meaning of these terms depends on the [writing mode](css_writing_modes.md).

[Block dimension](#block_dimension)

:   The dimension perpendicular to the flow of text within a line, i.e.,
    the vertical dimension in horizontal writing modes, and the
    horizontal dimension in vertical writing modes. For standard English
    text, it is the vertical dimension.

[Inline dimension](#inline_dimension)

:   The dimension parallel to the flow of text within a line, i.e., the
    horizontal dimension in horizontal writing modes, and the vertical
    dimension in vertical writing modes. For standard English text, it
    is the horizontal dimension.

### New properties and values

CSS was initially designed with only physical coordinates in its
controls. The module defines new flow--relative equivalents for many
[values](css_values_and_units.md) and
[properties](https://developer.mozilla.org/en-US/docs/Glossary/Property/CSS).

Some physical properties now have logical equivalents. Properties that
accept physical values (`top`, `bottom`, `left`, `right`) now also
accept flow-relative logical values (`block-start`, `block-end`,
`inline-start`, `inline-end`).

The transition to logical axes is ongoing and not fully defined by the
module; some properties don\'t yet have logical equivalents.

Reference
---------

### Properties for sizing

- [`block-size`](block-size.md)
- [`inline-size`](inline-size.md)
- [`max-block-size`](max-block-size.md)
- [`max-inline-size`](max-inline-size.md)
- [`min-block-size`](min-block-size.md)
- [`min-inline-size`](min-inline-size.md)

### Properties for margins

- [`margin`](margin.md) (`logical` [Experimental]
    keyword)
- [`margin-block`](margin-block.md)
- [`margin-block-end`](margin-block-end.md)
- [`margin-block-start`](margin-block-start.md)
- [`margin-inline`](margin-inline.md)
- [`margin-inline-end`](margin-inline-end.md)
- [`margin-inline-start`](margin-inline-start.md)

### Properties for paddings

- [`padding`](padding.md) (`logical` [Experimental]
    keyword)
- [`padding-block`](padding-block.md)
- [`padding-block-end`](padding-block-end.md)
- [`padding-block-start`](padding-block-start.md)
- [`padding-inline`](padding-inline.md)
- [`padding-inline-end`](padding-inline-end.md)
- [`padding-inline-start`](padding-inline-start.md)

### Properties for borders

- [`border-block`](border-block.md)
- [`border-block-color`](border-block-color.md)
- [`border-block-end`](border-block-end.md)
- [`border-block-end-color`](border-block-end-color.md)
- [`border-block-end-style`](border-block-end-style.md)
- [`border-block-end-width`](border-block-end-width.md)
- [`border-block-start`](border-block-start.md)
- [`border-block-start-color`](border-block-start-color.md)
- [`border-block-start-style`](border-block-start-style.md)
- [`border-block-start-width`](border-block-start-width.md)
- [`border-block-style`](border-block-style.md)
- [`border-block-width`](border-block-width.md)
- [`border-color`](border-color.md)
- [`border-inline`](border-inline.md)
- [`border-inline-color`](border-inline-color.md)
- [`border-inline-end`](border-inline-end.md)
- [`border-inline-end-color`](border-inline-end-color.md)
- [`border-inline-end-style`](border-inline-end-style.md)
- [`border-inline-end-width`](border-inline-end-width.md)
- [`border-inline-start`](border-inline-start.md)
- [`border-inline-start-color`](border-inline-start-color.md)
- [`border-inline-start-style`](border-inline-start-style.md)
- [`border-inline-start-width`](border-inline-start-width.md)
- [`border-inline-style`](border-inline-style.md)
- [`border-inline-width`](border-inline-width.md)
- [`border-style`](border-style.md)
- [`border-width`](border-width.md)

### Properties for border radius

- [`border-radius`](border-radius.md)
- [`border-start-start-radius`](border-start-start-radius.md)
- [`border-start-end-radius`](border-start-end-radius.md)
- [`border-end-start-radius`](border-end-start-radius.md)
- [`border-end-end-radius`](border-end-end-radius.md)

### Properties for positioning

- [`inset`](_Resources/Markup%20And%20Styling/css/inset.md)
- [`inset-block`](inset-block.md)
- [`inset-block-end`](inset-block-end.md)
- [`inset-block-start`](inset-block-start.md)
- [`inset-inline`](inset-inline.md)
- [`inset-inline-end`](inset-inline-end.md)
- [`inset-inline-start`](inset-inline-start.md)

### Properties for size containment

- [`contain-intrinsic-block-size`](contain-intrinsic-block-size.md)
- [`contain-intrinsic-inline-size`](contain-intrinsic-inline-size.md)

### Properties for scrolling

- [`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md)
- [`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md)
- [`overscroll-behavior-block`](overscroll-behavior-block.md)
- [`overscroll-behavior-inline`](overscroll-behavior-inline.md)

### Properties for floating

- [`clear`](clear.md) (`inline-end` and `inline-start` keywords)
- [`float`](float.md) (`inline-end` and `inline-start` keywords)

### Other properties

- [`caption-side`](caption-side.md) (`inline-end` and `inline-start`
    keywords)
- [`resize`](resize.md) (`block` and `inline` keywords)
- [`text-align`](text-align.md) (`end` and `start` keywords)

### Deprecated properties

- `offset-block-end` [Non-standard]
    [Deprecated] (now
    [`inset-block-end`](inset-block-end.md))
- `offset-block-start` [Non-standard]
    [Deprecated] (now
    [`inset-block-start`](inset-block-start.md))
- `offset-inline-end` [Non-standard]
    [Deprecated] (now
    [`inset-inline-end`](inset-inline-end.md))
- `offset-inline-start` [Non-standard]
    [Deprecated] (now
    [`inset-inline-start`](inset-inline-start.md))

### Unsupported properties

The following properties don\'t have logical equivalents:

- [`background-position-x`](background-position-x.md)
- [`background-position-y`](background-position-y.md)

### Unsupported values

The following properties accept only physical values:

- [`text-underline-position`](text-underline-position.md)
- [`box-shadow`](box-shadow.md)
- [`text-shadow`](text-shadow.md)
- [`clip-path`](clip-path.md)
- [`<position>`](position_value.md)
  - [`background-position`](background-position.md)
  - [`object-position`](object-position.md)
  - [`mask-position`](mask-position.md)
  - [`offset-position`](offset-position.md)
  - [`offset-anchor`](offset-anchor.md)
  - [`transform-origin`](transform-origin.md)
  - [`perspective-origin`](perspective-origin.md)

Guides
------

- [](basic_concepts_of_logical_properties_and_values.md)
- [](sizing.md)
- [](margins_borders_padding.md)
- [](floating_and_positioning.md)

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  ](https://drafts.csswg.org/css-logical/)

  -----------------------------------------------------------------------

Browser compatibility
---------------------

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values>

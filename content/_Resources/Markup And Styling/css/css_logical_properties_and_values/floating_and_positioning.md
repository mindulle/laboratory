Logical properties for floating and positioning
===============================================

The [Logical Properties and Values
specification](https://drafts.csswg.org/css-logical/) contains logical
mappings for the physical values of [`float`](float.md) and
[`clear`](clear.md), and also for the positioning properties used with
[positioned layout](css_positioned_layout.md). This guide takes a look
at how to use these.

Mapped properties and values
----------------------------

The table below details the properties and values discussed in this
guide along with their physical mappings. They assume a horizontal
[`writing-mode`](writing-mode.md), with a left-to-right direction.

  Logical property or value                       Physical property or value
  ----------------------------------------------- --------------------------------------
  [`float`](float.md): inline-start               [`float`](float.md): left
  [`float`](float.md): inline-end                 [`float`](float.md): right
  [`clear`](clear.md): inline-start               [`clear`](clear.md): left
  [`clear`](clear.md): inline-end                 [`clear`](clear.md): right
  [`inset-inline-start`](inset-inline-start.md)   [`left`](left.md)
  [`inset-inline-end`](inset-inline-end.md)       [`right`](right.md)
  [`inset-block-start`](inset-block-start.md)     [`top`](top.md)
  [`inset-block-end`](inset-block-end.md)         [`bottom`](bottom.md)
  [`text-align`](text-align.md): start            [`text-align`](text-align.md): left
  [`text-align`](text-align.md): end              [`text-align`](text-align.md): right

In addition to these mapped properties there are some additional
shorthand properties made possible by being able to address block and
inline dimensions. These have no mapping to physical properties, aside
from the [`inset`](_Resources/Markup%20And%20Styling/css/inset.md) property.

  Logical property                    Purpose
  ----------------------------------- ---------------------------------------------------------------------------------
  [`inset-inline`](inset-inline.md)   Sets both of the above inset values for the inline dimension simultaneously.
  [`inset-block`](inset-block.md)     Sets both of the above inset values for the block dimension simultaneously.
  [`inset`](_Resources/Markup%20And%20Styling/css/inset.md)                 Sets all four inset values simultaneously with physical mapping of multi-value.

Float and clear example
-----------------------

The physical values used with the [`float`](float.md) and
[`clear`](clear.md) properties are `left`, `right` and `both`. The
Logical Properties specification defines the values `inline-start` and
`inline-end` as mappings for `left` and `right`.

In the example below I have two boxes --- the first has the box floated
with `float: left`, the second with `float: inline-start`. If you change
the `writing-mode` to `vertical-rl` or the `direction` to `rtl` you will
see that the left-floated box always sticks to the left, whereas the
`inline-start`-floated item follows the `direction` and `writing-mode`.

Example: Inset properties for positioned layout
-----------------------------------------------

Positioning generally allows us to position an element in a manner
relative to its containing block --- we essentially inset the item
relative to where it would fall based on normal flow. To do this we have
historically used the physical properties [`top`](top.md),
[`right`](right.md), [`bottom`](bottom.md) and [`left`](left.md).

These properties take a length or a percentage as a value, and relate to
the user\'s screen dimensions.

New properties have been created in the Logical Properties specification
for when you want the positioning to relate to the flow of text in your
writing mode. These are as follows:
[`inset-block-start`](inset-block-start.md),
[`inset-block-end`](inset-block-end.md),
[`inset-inline-start`](inset-inline-start.md) and
[`inset-inline-end`](inset-inline-end.md).

In the below example I have used the `inset-block-start` and
`inset-inline-end` properties to position the blue box using absolute
positioning inside the area with the grey dotted border, which has
`position: relative`. Change the `writing-mode` property to
`vertical-rl`, or add `direction: rtl`, and see how the flow relative
box stays with the text direction.

New two- and four-value shorthands
----------------------------------

As with other properties in the specification we have some new shorthand
properties, which give the ability to set two or four values at once.

- [`inset`](_Resources/Markup%20And%20Styling/css/inset.md) --- sets all four sides together with physical
    mapping.
- [`inset-inline`](inset-inline.md) --- sets both logical inline
    insets.
- [`inset-block`](inset-block.md) --- sets both logical block insets.

Example: Logical values for text-align
--------------------------------------

The [`text-align`](text-align.md) property has logical values that
relate to text direction --- rather than using `left` and `right` we can
use `start` and `end`. In the below example I have set
`text-align: right` in the first block and `text-align: end` in the
second.

If you change the value of `direction` to `rtl` you will see that the
alignment stays to the right for the first block, but goes to the
logical end on the left in the second.

This works more consistently when using box alignment that uses start
and end rather than physical directions for alignment.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values/Floating_and_positioning>

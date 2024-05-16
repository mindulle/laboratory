Flow layout and writing modes
=============================

The CSS 2.1 specification, which details how normal flow behaves,
assumes a horizontal writing mode.
[Layout](block_and_inline_layout_in_normal_flow.md) properties should work
in the same way in vertical writing modes. In this guide, we look at how
flow layout behaves when used with different document writing modes.

This is not a comprehensive guide to the use of writing modes in CSS,
the aim here is to document the areas where flow layout interacts with
writing modes in possibly unanticipated ways. The [See also](#see_also)
section provides links to more writing modes resources.

Writing modes specification
---------------------------

The CSS Writing Modes Level 3 Specification defines the impact a change
the document writing mode has on flow layout. In the writing modes
introduction, [the specification
says](https://drafts.csswg.org/css-writing-modes-3/#text-flow),

> \"A writing mode in CSS is determined by the
> [`writing-mode`](writing-mode.md), [`direction`](direction.md), and
> [`text-orientation`](text-orientation.md) properties. It is defined
> primarily in terms of its inline base direction and block flow
> direction.\"

The specification defines the *inline base direction* as the direction
in which content is ordered on a line. This defines the start and end of
the inline direction. The start is where sentences start and the end is
where a line of text ends before it would begin to wrap onto a new line.

The *block flow direction* is the direction in which boxes, for example
paragraphs, stack in that writing mode. The CSS writing-mode property
controls the block flow direction. If you want to change your page, or
part of your page, to `vertical-lr` then you can set
`writing-mode: vertical-lr` on the element and this will change the
direction of the blocks and therefore the inline direction as well.

While certain languages will use a particular writing mode or text
direction, we can also use these properties for creative effect, such as
running a heading vertically.

Block flow direction
--------------------

The [`writing-mode`](writing-mode.md) property accepts the values
`horizontal-tb`, `vertical-rl` and `vertical-lr`. These values control
the direction that blocks flow on the page. The initial value is
`horizontal-tb,` which is a top to bottom block flow direction with a
horizontal inline direction. Left to right languages, such as English,
and Right to left languages, such as Arabic, are all `horizontal-tb`.

The following example shows blocks using `horizontal-tb`.

The value `vertical-rl` gives you a right-to-left block flow direction
with a vertical inline direction, as shown in the next example.

The final example demonstrates the third possible value for
`writing-mode` --- `vertical-lr`. This gives you a left-to-right block
flow direction and a vertical inline direction.

Nested writing modes
--------------------

When a nested box is assigned a different writing mode to its parent,
then an inline level box will display as if it has
`display: inline-block`.

A block-level box will establish a new block formatting context, meaning
that if its inner display type would be `flow`, it will get a computed
display type of `flow-root`. This is shown in the next example where the
box which displays as `horizontal-tb` contains a float which is
contained due to its parent establishing a new BFC.

Replaced elements
-----------------

Replaced elements such as images will not change their orientation based
on the `writing-mode` property. However, replaced elements such as form
controls which include text, should match the writing mode in use.

Logical properties and values
-----------------------------

Once you are working in writing modes other than `horizontal-tb` many of
the properties and values that are mapped to the physical dimensions of
the screen seem strange. For example, if you give a box a width of
100px, in `horizontal-tb` that would control the size in the inline
direction. In `vertical-lr` it controls the size in the block direction
because it does not rotate with the text.

Therefore, we have new properties of [`block-size`](block-size.md) and
[`inline-size`](inline-size.md). If we give our block an `inline-size`
of 100px, it doesn\'t matter whether we are in a horizontal or a
vertical writing mode, `inline-size` will always mean the size in the
inline direction.

The [](css_logical_properties_and_values.md) module includes logical
versions of the properties that control margins, padding and borders as
well as other mappings for things that we have typically used physical
directions to specify.

Summary
-------

In most cases, flow layout works as you would expect it to when changing
the writing mode of the document or parts of the document. This can be
used to properly typeset vertical languages or for creative reasons. CSS
is making this easier by way of introducing logical properties and
values so that when working in a vertical writing mode sizing can be
based on element\'s inline and block size. This will be useful when
creating components which can work in different writing-modes.

See also
--------

- [Writing Modes](css_writing_modes.md)
- [Writing modes and CSS
    layout](https://www.smashingmagazine.com/2019/08/writing-modes-layout/)
    on Smashing Magazine (2019)
- [CSS writing modes](https://24ways.org/2016/css-writing-modes/) on
    24ways.org (2016)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flow_layout/Flow_layout_and_writing_modes>

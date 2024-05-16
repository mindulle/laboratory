Styling columns
===============

As column boxes created inside multi-column (*multicol*) containers are
anonymous boxes, styling individual columns is not possible, but we can
style the gaps between the columns and the container in general. This
guide explains how to change the gap and style rules between columns.

Column gaps
-----------

The gap between columns is controlled using the
[`column-gap`](column-gap.md) or [`gap`](gap.md) property. The
`column-gap` property is defined in the [](css_multicol_layout.md) module. The `gap` property is defined in
the [box alignment](css_box_alignment.md) module. This is a unified
property to define gaps between boxes in all layouts that support gaps,
including [](_Resources/Markup%20And%20Styling/css/css_grid_layout/box_alignment_in_grid_layout.md) and [](mastering_wrapping_of_flex_items.md).

The initial value of `column-gap` is `1em`, which prevents columns from
running into each other. In other layout methods, `column-gap` is
supported as a synonym for `gap`, but with an initial value of `0`. The
keyword value `normal` sets `column-gap` to the initial value.

You can change the gap by using any [`<length>`](length.md) value. In
the example below, the `column-gap` is set to `40px`.

The allowed value for `column-gap` is a
[`<length-percentage>`](length-percentage.md), meaning percentages are
allowed. Percentage values for `column-gap` are calculated as a
percentage of the width of the multicol container.

Column rules
------------

The specification defines [`column-rule-width`](column-rule-width.md),
[`column-rule-style`](column-rule-style.md) and
[`column-rule-color`](column-rule-color.md), providing a shorthand
[`column-rule`](column-rule.md). These properties work in exactly the
same way as the [`border`](border.md) properties: any
[`<line-style>`](line-style.md) can be used as a `column-rule-style`,
just as for valid [`border-style`](border-style.md).

These properties are applied to the element, which is the multicol
container, and therefore, all columns will have the same rule. Rules are
only drawn between columns and not on the outer edges. Rules are also
only drawn between columns that have content.

In this next example, a 5px-dotted rule with a color of `rebeccapurple`
has been created using the longhand values.

Note that the rule itself does not take up any space: a wide rule will
not push the columns apart to make space for the rule. Instead, the rule
overlays the gap.

The example below uses a very wide rule of `40px` and a `10px` gap. The
rule displays under the column content. To make space on both sides of
the rule, the gap would need to be increased to be larger than `40px`.

Next steps
----------

This article details all the current ways in which column boxes can be
styled. In the next guide, we will take a look at making elements inside
a container [span across all columns](spanning_balancing_columns.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Styling_columns>

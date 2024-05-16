Introduction to the CSS basic box model
=======================================

When laying out a document, the browser\'s rendering engine represents
each element as a rectangular box according to the standard **CSS basic
box model**. CSS determines the size, position, and properties (color,
background, border size, etc.) of these boxes.

Every box is composed of four parts (or *areas*), defined by their
respective edges: the *content edge*, *padding edge*, *border edge*, and
*margin edge*.

Content area
------------

The **content area**, bounded by the content edge, contains the \"real\"
content of the element, such as text, an image, or a video player. Its
dimensions are the *content width* (or *content-box width*) and the
*content height* (or *content-box height*). It often has a background
color or background image.

If the [`box-sizing`](box-sizing.md) property is set to `content-box`
(default) and if the element is a block element, the content area\'s
size can be explicitly defined with the [`width`](_Resources/Markup%20And%20Styling/css/width.md),
[`min-width`](min-width.md), [`max-width`](max-width.md),
[`height`](_Resources/Markup%20And%20Styling/css/height.md), [`min-height`](min-height.md), and
[`max-height`](max-height.md) properties.

Padding area
------------

The **padding area**, bounded by the padding edge, extends the content
area to include the element\'s padding. Its dimensions are the
*padding-box width* and the *padding-box height*.

The thickness of the padding is determined by the
[`padding-top`](padding-top.md), [`padding-right`](padding-right.md),
[`padding-bottom`](padding-bottom.md),
[`padding-left`](padding-left.md), and shorthand [`padding`](padding.md)
properties.

Border area
-----------

The **border area**, bounded by the border edge, extends the padding
area to include the element\'s borders. Its dimensions are the
*border-box width* and the *border-box height*.

The thickness of the borders are determined by the
[`border-width`](border-width.md) and shorthand [`border`](border.md)
properties. If the [`box-sizing`](box-sizing.md) property is set to
`border-box`, the border area\'s size can be explicitly defined with the
[`width`](_Resources/Markup%20And%20Styling/css/width.md), [`min-width`](min-width.md),
[`max-width`](max-width.md), [`height`](_Resources/Markup%20And%20Styling/css/height.md),
[`min-height`](min-height.md), and [`max-height`](max-height.md)
properties. When there is a background
([`background-color`](background-color.md) or
[`background-image`](background-image.md)) set on a box, it extends to
the outer edge of the border (i.e. extends underneath the border in
z-ordering). This default behavior can be altered with the
[`background-clip`](background-clip.md) CSS property.

Margin area
-----------

The **margin area**, bounded by the margin edge, extends the border area
to include an empty area used to separate the element from its
neighbors. Its dimensions are the *margin box width* and the *margin box
height*.

The size of the margin area is determined by the
[`margin-top`](margin-top.md), [`margin-right`](margin-right.md),
[`margin-bottom`](margin-bottom.md), [`margin-left`](margin-left.md),
and shorthand [`margin`](margin.md) properties. When [](mastering_margin_collapsing.md) occurs, the margin area is not
clearly defined since margins are shared between boxes.

Finally, note that for non-replaced inline elements, the amount of space
taken up (the contribution to the height of the line) is determined by
the [`line-height`](line-height.md) property, even though the borders
and padding are still displayed around the content.

See also
--------

- [Layout and the containing block](containing_block.md)
- [Introducing the CSS Cascade](cascade.md)
- [Cascade, specificity, and
    inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
- CSS key concepts:
  - [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
  - [At-rules](at-rule.md)
  - [Comments](comments.md)
  - [Specificity](specificity.md)
  - [Inheritance](inheritance.md)
  - [Layout modes](layout_mode.md)
  - [Visual formatting models](visual_formatting_model.md)
  - [Margin collapsing](mastering_margin_collapsing.md)
  - Values
    - [Initial values](initial_value.md)
    - [Computed values](computed_value.md)
    - [Used values](used_value.md)
    - [Actual values](actual_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Introduction_to_the_CSS_box_model>

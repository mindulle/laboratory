CSS flexible box layout
=======================

The **CSS flexible box layout** module defines a CSS box model optimized
for user interface design, and the layout of items in one dimension. In
the flex layout model, the children of a flex container can be laid out
in any direction, and can \"flex\" their sizes, either growing to fill
unused space or shrinking to avoid overflowing the parent. Both
horizontal and vertical alignment of the children can be easily
manipulated.

Basic example
-------------

In the following example a container has been set to `display: flex`,
which means that the three child items become flex items. The value of
`justify-content` has been set to `space-between` in order to space the
items out evenly on the main axis. An equal amount of space is placed
between each item with the left and right items being flush with the
edges of the flex container. You can also see that the items are
stretching on the cross axis, due to the default value of `align-items`
being `stretch`. The items stretch to the height of the flex container,
making them each appear as tall as the tallest item.

Reference
---------

### Properties

- [`flex`](flex.md)
- [`flex-basis`](flex-basis.md)
- [`flex-direction`](flex-direction.md)
- [`flex-flow`](flex-flow.md)
- [`flex-grow`](flex-grow.md)
- [`flex-shrink`](flex-shrink.md)
- [`flex-wrap`](flex-wrap.md)
- [`order`](order.md)

### Properties for alignment

The properties `align-content`, `align-self`, `align-items` and
`justify-content` initially appeared in the Flexbox specification, but
are now defined in Box Alignment. The Flexbox spec now refers to the Box
Alignment specification for up to date definitions. Also additional
alignment properties are now defined in Box Alignment.

- [`justify-content`](justify-content.md)
- [`align-content`](align-content.md)
- [`align-items`](align-items.md)
- [`align-self`](align-self.md)
- [`place-content`](place-content.md)
- [`place-items`](place-items.md)
- [`row-gap`](row-gap.md)
- [`column-gap`](column-gap.md)
- [`gap`](gap.md)

Guides
------

[Basic concepts of flexbox](basic_concepts_of_flexbox.md)

:   An overview of the features of Flexbox

[Relationship of flexbox to other layout methods](relationship_of_flexbox_to_other_layout_methods.md)

:   How Flexbox relates to other layout methods, and other CSS
    specifications

[Aligning items in a flex container](aligning_items_in_a_flex_container.md)

:   How the Box Alignment properties work with Flexbox.

[Ordering flex items](ordering_flex_items.md)

:   Explaining the different ways to change the order and direction of
    items, and covering the potential issues in doing so.

[Controlling ratios of flex items along the main axis](controlling_ratios_of_flex_items_along_the_main_axis.md)

:   Explaining the flex-grow, flex-shrink and flex-basis properties.

[Mastering wrapping of flex items](mastering_wrapping_of_flex_items.md)

:   How to create flex containers with multiple lines and control the
    display of the items in those lines.

[Typical use cases of flexbox](typical_use_cases_of_flexbox.md)

:   Common design patterns that are typical Flexbox use cases.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Flexible Box Layout Module Level 1\
  ](https://drafts.csswg.org/css-flexbox/)

  -----------------------------------------------------------------------

See also
--------

- Glossary terms:
  - [Flexbox](https://developer.mozilla.org/en-US/docs/Glossary/Flexbox)
  - [Flex
        Container](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Container)
  - [Flex
        Item](https://developer.mozilla.org/en-US/docs/Glossary/Flex_Item)
  - [Main
        Axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis)
  - [Cross
        Axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis)
  - [Flex](https://developer.mozilla.org/en-US/docs/Glossary/Flex)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout>

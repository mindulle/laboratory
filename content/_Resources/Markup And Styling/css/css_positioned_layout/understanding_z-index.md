Understanding z-index
=====================

In the most basic cases,
[HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) pages can be
considered two-dimensional, because text, images, and other elements are
arranged on the page without overlapping. In this case, there is a
single rendering flow, and all elements are aware of the space taken by
others. The [`z-index`](z-index.md) attribute lets you adjust the order
of the layering of objects when rendering content.

> *In CSS 2.1, each box has a position in three dimensions. In addition
> to their horizontal and vertical positions, boxes lie along a
> \"z-axis\" and are formatted one on top of the other. Z-axis positions
> are particularly relevant when boxes overlap visually.*

(from [CSS 2.1 Section 9.9.1 - Layered
presentation](https://www.w3.org/TR/CSS21/visuren.html#z-index))

This means that CSS style rules allow you to position boxes on layers in
addition to the default rendering layer (layer 0). The position on an
imaginary z-axis of each layer is expressed as an integer representing
the stacking order for rendering. Greater numbers mean closer to the
observer. Control the position on this z-axis with the CSS `z-index`
property.

Using `z-index` appears extremely easy: a single property assigned a
single integer number with an easy-to-understand behavior. When
`z-index` is applied to complex hierarchies of HTML elements, its
behavior can be hard to understand or predict. This is due to complex
stacking rules. In fact, a dedicated section has been reserved in the
CSS specification [CSS-2.1 Appendix
E](https://www.w3.org/TR/CSS21/zindex.html) to explain these rules
better.

This guide will try to explain those rules, with some simplification and
several examples.

Articles
--------

1. [](stacking_without_z-index.md): The
    stacking rules that apply when `z-index` is not used.
2. [](stacking_floating_elements.md): How
    floating elements are handled with stacking.
3. [Using z-index](using_z-index.md): How to use
    `z-index` to change default stacking.
4. [Stacking context](stacking_context.md): Notes on
    the stacking context.

Examples
--------

1. [](stacking_context_example_1.md): 2-level HTML
    hierarchy, `z-index` on the last level
2. [](stacking_context_example_2.md): 2-level HTML
    hierarchy, `z-index` on all levels
3. [](stacking_context_example_3.md): 3-level HTML
    hierarchy, `z-index` on the second level

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index>

In flow and out of flow
=======================

The [previous guide](block_and_inline_layout_in_normal_flow.md) explained
block and inline layout in normal flow. All elements that are in flow
will be laid out using this method.

The following example contains a heading, paragraph, a list and a final
paragraph which contains a `strong` element. The heading and paragraphs
are block level, the `strong` element inline. The list is displayed
using flexbox to arrange the items into a row, however it too is
participating in block and inline layout - the container has an outside
`display` type of `block`.

All of the elements can be said to be in flow. Appearing on the page in
the order that they are in the source.

Taking an item out of flow
--------------------------

All elements are in-flow apart from:

- floated items
- items with `position: absolute` (including `position: fixed` which
    acts in the same way)
- the root element (`html`)

Out of flow items create a new Block Formatting Context (BFC) and
therefore everything inside them can be seen as a mini layout, separate
from the rest of the page. The root element therefore is out of flow, as
the container for everything in our document, and establishes the Block
Formatting Context for the document.

### Floated items

In this example, there is a `div` and then two paragraphs. A background
color has been added to the paragraphs, and the `div` is floated left.
The `div` is now out of flow.

As a float it is first laid out according to where it would be in normal
flow, then taken out of flow and moved to the left as far as possible.

You can see the background color of the following paragraph running
underneath, it is only the line boxes of that paragraph that have been
shortened to cause the effect of wrapping content around the float. The
box of our paragraph is still displaying according to the rules of
normal flow. This is why, to make space around a floated item, you must
add a margin to the item, in order to push the line boxes away from it.
You cannot apply anything to the following in-flow content to achieve
that.

### Absolute positioning

Giving an item `position: absolute` or `position: fixed` removes it from
flow, and any space that it would have taken up is removed. In the next
example I have three paragraph elements, the second element has
`position: absolute`, with offset values of `top: 30px` and
`right: 30px`. It has been removed from document flow.

Using `position: fixed` also removes the item from flow, however the
offsets are based on the viewport rather than the containing block.

When taking an item out of flow with positioning, you will need to
manage the possibility of content overlapping. Out of flow essentially
means that the other elements on your page no longer know that element
exists so will not respond to it.

### Relative positioning and flow

If you give an item relative positioning with `position: relative`, it
remains in flow. However, you are then able to use the offset values to
push it around. The space that it would have been placed in normal flow
is reserved however, as you can see in the example below.

When you do anything to remove or shift an item from where it would be
placed in normal flow, you can expect to need to do some managing of the
content and the content around it to prevent overlaps. Whether that
involves clearing floats, or ensuring that an element with
`position: absolute` does not sit on top of some other content. For this
reason methods which remove elements from being in-flow should be used
with understanding of the effect that they have.

Summary
-------

In this guide, we have covered the ways to take an element out of flow
in order to achieve some very specific types of positioning. In the next
guide we will look at a related issue, that of creating a [Block
Formatting
Context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context),
in [Formatting Contexts Explained](introduction_to_formatting_contexts.md).

See also
--------

- [Positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)
    in the CSS Layout learn area

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flow_layout/In_flow_and_out_of_flow>

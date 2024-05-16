Aligning items in a flex container
==================================

One of the reasons that flexbox quickly caught the interest of web
developers is that it brought proper alignment capabilities to the web
for the first time. It enabled proper vertical alignment, so we can at
last easily center a box. In this guide, we will take a thorough look at
how the alignment and justification properties work in Flexbox.

To center our box we use the `align-items` property to align our item on
the cross axis, which in this case is the block axis running vertically.
We use `justify-content` to align the item on the main axis, which in
this case is the inline axis running horizontally.

You can take a look at the code of this example below. Change the size
of the container or nested element and the nested element always remains
centered.

Properties that control alignment
---------------------------------

The properties we will look at in this guide are as follows.

- [`justify-content`](justify-content.md) --- controls alignment of
    all items on the main axis.
- [`align-items`](align-items.md) --- controls alignment of all items
    on the cross axis.
- [`align-self`](align-self.md) --- controls alignment of an
    individual flex item on the cross axis.
- [`align-content`](align-content.md) --- described in the spec as for
    \"packing flex lines\"; controls space between flex lines on the
    cross axis.
- [`gap`](gap.md), [`column-gap`](column-gap.md), and
    [`row-gap`](row-gap.md) --- used to create gaps or gutters between
    flex items.

We will also discover how auto margins can be used for alignment in
flexbox.

The Cross Axis
--------------

The `align-items` and `align-self` properties control alignment of our
flex items on the cross axis, down the columns if `flex-direction` is
`row` and along the row if `flex-direction` is `column`.

We are making use of cross-axis alignment in the most simple flex
example. If we add `display: flex` to a container, the child items all
become flex items arranged in a row. They will all stretch to be as tall
as the tallest item, as that item is defining the height of the items on
the cross axis. If your flex container has a height set, then the items
will stretch to that height, regardless of how much content is in the
item.

The reason the items become the same height is that the initial value of
`align-items`, the property that controls alignment on the cross axis,
is set to `stretch`.

We can use other values to control how the items align:

- `align-items: flex-start`
- `align-items: flex-end`
- `align-items: center`
- `align-items: stretch`
- `align-items: baseline`

In the live example below, the value of `align-items` is `stretch`. Try
the other values and see how all of the items align against each other
in the flex container.

### Aligning one item with `align-self`

The `align-items` property sets the `align-self` property on all of the
flex items as a group. This means you can explicitly declare the
`align-self` property to target a single item. The `align-self` property
accepts all of the same values as `align-items` plus a value of `auto`,
which will reset the value to that which is defined on the flex
container.

In this next live example, the flex container has
`align-items: flex-start`, which means the items are all aligned to the
start of the cross axis. I have targeted the first item using a
`first-child` selector and set that item to `align-self: stretch`;
another item has been selected using its class of `selected` and given
`align-self: center`. You can change the value of `align-items` or
change the values of `align-self` on the individual items to see how
this works.

### Changing the main axis

So far we have looked at the behavior when our `flex-direction` is
`row`, and while working in a language written top to bottom. This means
that the main axis runs along the row horizontally, and our cross axis
alignment moves the items up and down.

![Three items, the first aligned to flex-start, second to center, third to flex-end. Aligning on the vertical
axis.](data:image/png;base64,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)

If we change our `flex-direction` to column, `align-items` and
`align-self` will align the items to the left and right.

![Three items, the first aligned to flex-start, second to center, third to flex-end. Aligning on the horizontal
axis.](data:image/png;base64,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)

You can try this out in the example below, which has a flex container
with `flex-direction: column` yet otherwise is exactly the same as the
previous example.

Aligning content on the cross axis --- the align-content property
-----------------------------------------------------------------

So far we have been aligning the items, or an individual item inside the
area defined by the flex-container. If you have a wrapped multiple-line
flex container then you might also want to use the `align-content`
property to control the distribution of space between the rows. In the
specification this is described as [packing flex
lines](https://drafts.csswg.org/css-flexbox/#align-content-property).

For `align-content` to work you need more height in your flex container
than is required to display the items. It then works on all the items as
a set, and dictates what happens with that free space, and the alignment
of the entire set of items within it.

The `align-content` property takes the following values:

- `align-content: flex-start`
- `align-content: flex-end`
- `align-content: center`
- `align-content: space-between`
- `align-content: space-around`
- `align-content: stretch`
- `align-content: space-evenly` (not defined in the Flexbox
    specification)

In the live example below, the flex container has a height of 400
pixels, which is more than needed to display our items. The value of
`align-content` is `space-between`, which means that the available space
is shared out *between* the flex lines, which are placed flush with the
start and end of the container on the cross axis.

Try out the other values to see how the `align-content` property works.

Once again we can switch our `flex-direction` to `column` in order to
see how this property behaves when we are working by column. As before,
we need enough space in the cross axis to have some free space after
displaying all of the items.

**Note:** The value `space-evenly` is not defined in the flexbox
specification and is a later addition to the Box Alignment
specification. Browser support for this value is not as good as that of
the values defined in the flexbox spec.

Aligning content on the main axis
---------------------------------

Now that we have seen how alignment works on the cross axis, we can take
a look at the main axis. Here we only have one property available to us
--- `justify-content`. This is because we are only dealing with items as
a group on the main axis. With `justify-content` we control what happens
with available space, should there be more space than is needed to
display the items.

In our initial example with `display: flex` on the container, the items
display as a row and all line up at the start of the container. This is
due to the initial value of `justify-content` being `flex-start`. Any
available space is placed at the end of the items.

The `justify-content` property accepts the same values as
`align-content`.

- `justify-content: flex-start`
- `justify-content: flex-end`
- `justify-content: center`
- `justify-content: space-between`
- `justify-content: space-around`
- `justify-content: space-evenly` (not defined in the Flexbox
    specification)

In the example below, the value of `justify-content` is `space-between`.
The available space after displaying the items is distributed between
the items. The left and right item line up flush with the start and end.

If the main axis is in the block direction because `flex-direction` is
set to `column`, then `justify-content` will distribute space between
items in that dimension as long as there is space in the flex container
to distribute.

### Alignment and Writing Modes

Remember that with all of these alignment methods, the values of
`flex-start` and `flex-end` are writing mode-aware. If the value of
`justify-content` is `flex-start` and the writing mode is left-to-right
as in English, the items will line up starting at the left side of the
container.

However if the writing mode is right-to-left as in Arabic, the items
will line up starting at the right side of the container.

The live example below has the `direction` property set to `rtl` to
force a right-to-left flow for our items. You can remove this, or change
the values of `justify-content` to see how flexbox behaves when the
start of the inline direction is on the right.

Alignment and flex-direction
----------------------------

The start line will also change if you change the `flex-direction`
property --- for example using `row-reverse` instead of `row`.

In this next example I have items laid out with
`flex-direction: row-reverse` and `justify-content: flex-end`. In a left
to right language the items all line up on the left. Try changing
`flex-direction: row-reverse` to `flex-direction: row`. You will see
that the items now move to the right-hand side.

While this may all seem a little confusing, the rule to remember is that
unless you do something to change it, flex items lay themselves out in
the direction that words are laid out in the language of your document
along the inline, row axis. `flex-start` will be where the start of a
sentence of text would begin.

You can switch them to display in the block direction for the language
of your document by selecting `flex-direction: column`. Then
`flex-start` will then be where the top of your first paragraph of text
would start.

If you change `flex-direction` to one of the reverse values, then they
will lay themselves out from the end axis and in the reverse order to
the way words are written in the language of your document. `flex-start`
will then change to the end of that axis --- so to the location where
your lines would wrap if working in rows, or at the end of your last
paragraph of text in the block direction.

Using auto margins for main axis alignment
------------------------------------------

We don\'t have a `justify-items` or `justify-self` property available to
us on the main axis as our items are treated as a group on that axis.
However it is possible to do some individual alignment in order to
separate an item or a group of items from others by using auto margins
along with flexbox.

A common pattern is a navigation bar where some key items are aligned to
the right, with the main group on the left. You might think that this
should be a use case for a `justify-self` property, however consider the
image below. I have three items on one side and two on the other. If I
were able to use `justify-self` on item *d*, it would also change the
alignment of item *e* that follows, which may or may not be my
intention.

Instead we can target item 4 and separate it from the first three items
by giving it a `margin-left` value of `auto`. Auto margins will take up
all of the space that they can in their axis --- it is how centering a
block with margin auto left and right works. Each side tries to take as
much space as it can, and so the block is pushed into the middle.

In this live example, I have flex items arranged into a row with the
basic flex values, and the class `push` has `margin-left: auto`. You can
try removing this, or adding the class to another item to see how it
works.

Creating gaps between items
---------------------------

To create a gap between flex items, use the [`gap`](gap.md),
[`column-gap`](column-gap.md), and [`row-gap`](row-gap.md) properties.
The [`column-gap`](column-gap.md) property creates gaps between items in
a row. The [`row-gap`](row-gap.md) property creates gaps between flex
lines, when you have [`flex-wrap`](flex-wrap.md) set to `wrap`. The
[`gap`](gap.md) property is a shorthand that sets both together.

See also
--------

- [Box alignment](css_box_alignment.md)
- [](box_alignment_in_flexbox.md)
- [](_Resources/Markup%20And%20Styling/css/css_box_alignment/box_alignment_in_grid_layout.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Aligning_items_in_a_flex_container>

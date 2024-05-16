Spanning and balancing columns
==============================

In this guide, we look at how to make elements span across columns
inside the multi-column (*multicol*) container and how to control how
the columns are filled.

Spanning the columns
--------------------

To cause an item to span across columns, use the
[`column-span`](column-span.md) property with a value of `all`. This
will cause the element to become a *spanner*, spanning all the columns.

Any descendant element of the multicol container may be turned into a
spanner, including both direct and indirect children. For example, a
heading nested directly inside the container could become a spanner, as
could a heading nested inside a
[`<section>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section)
nested inside the multicol container.

In the example below, the `<h2>` element is set to `column-span: all`
and spans all of the columns.

In this second example, the heading is inside an
[`<article>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article)
element, yet still spans the content as expected.

When a spanner is introduced, it breaks the flow of columns; columns
restart after the spanner, effectively creating a new set of column
boxes. The content does not jump over a spanning element.

### Limitations of column-span

The `column-span` can have only two values. The initial value `none`
means the item does not span and remains within a column. The value
`all` means the item spans all of the columns. There are no values that
enable partial spanning, such as having an item span two out of three
columns.

### Things to watch out for

If the spanning element is inside another element with margins, padding,
and a border or background color, the box may appear above the spanner
with the rest of the content being displayed below. For this reason,
care should be taken when setting an element to span all the columns,
ensuring this scenario is accounted for.

Additionally, if a spanning element appears later in the content, it can
cause unexpected or unwanted behavior when there is not enough content
to create columns after the spanner. Use spanning carefully and test at
various breakpoints to make sure you get the effect you intended.

Filling and balancing columns
-----------------------------

A balanced set of columns is where all columns have approximately the
same amount of content. Filling and balancing are relevant when the
amount of content does not match the amount of space provided, such as
when a [`height`](_Resources/Markup%20And%20Styling/css/height.md) is declared on the container.

The initial value for [`column-fill`](column-fill.md) is `balance`. The
value of `balance` means all columns are as balanced as possible. In
fragmented contexts, such as [paged media](css_paged_media.md), only the
last fragment is balanced. This means that on the last page, the final
set of column boxes is balanced.

The other balancing value, `balance-all`, balances all columns in
fragmented contexts.

The columns in this example contain an image and some text, which are
balanced. The image, which cannot break, is in the first column. The
other columns are balanced, filling with equal amounts of text.

The `auto` value for `column-fill` fills a column sequentially, filling
the first column in the inline-start direction, before placing content
in subsequent columns, rather than balancing and filling all the columns
equally. In this example, we changed `column-fill` to `auto`. The
columns are filled to the height of the container, leaving empty columns
at the end.

Next steps
----------

In the next guide, you will learn [](handling_overflow_in_multicol_layout.md) within columns and when
there are more columns than can fit in the container.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Spanning_balancing_columns>

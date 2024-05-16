Handling content breaks in multi-column layout
==============================================

Content between column boxes in a multicol layout breaks in the same way
that it breaks between pages in paged media. In both contexts, you can
control where and how content breaks by using properties of the [](css_fragmentation.md) module. In this guide, we see how
fragmentation works in a *multi-column container* or *multicol
container* for short.

Fragmentation basics
--------------------

The CSS fragmentation module provides details on how content breaks
between the fragmentation containers or *fragmentainers*. The
[multi-column layout](css_multicol_layout.md) module, on the other hand,
defines the [`break-after`](break-after.md),
[`break-before`](break-before.md), and [`break-inside`](break-inside.md)
properties that provide some control within and between columns. In
multicol layout, a column box is a fragment container.

A column box can contain other markup and there are many places where a
break would not be ideal. For example, we would generally prefer that
the caption of an image not be separated into a new column away from the
image it refers to. Also, ending a column with a heading looks strange.
The multicol fragmentation properties give us ways to exercise some
control over this.

There are various places we might want to control our breaks:

- Breaks inside boxes, for example inside a figure element.
- Breaks before and after boxes, which would include our heading
    example above.
- Breaks between lines.

Breaks inside boxes
-------------------

To control breaks inside boxes use the [`break-inside`](break-inside.md)
property. This property takes values of:

- `auto`
- `avoid`
- `avoid-page`
- `avoid-column`
- `avoid-region`

In the example below, we have applied break-inside to the figure element
to prevent the caption from becoming separated from the image.

Breaks before and after boxes
-----------------------------

The [`break-before`](break-before.md) and
[`break-after`](break-after.md) properties are used to control breaks
before and after elements. They take the following values when in a
multicol context:

- auto
- avoid
- avoid-column
- column

In this next example, we are forcing a column break before an `h2`
element.

Breaks between lines
--------------------

The [`orphans`](orphans.md) and [`widows`](widows.md) properties, part
of the CSS fragmentation module, are also useful and worth mentioning.
The `orphans` property controls the number of lines left on their own at
the end of a fragment. The `widows` property controls the number left on
their own at the start of a fragment.

The `orphans` and `widows` properties take an [`<integer>`](integer.md)
as a value, which represents the number of lines to keep together at the
end and start of a fragment, respectively. Note that these properties
only work inside a block container, such as a paragraph. If the block
has fewer lines in it than the number that you specify as a value, all
lines will be kept together.

In the example below, we are using the `orphans` property to control the
number of lines left at the bottom of a column. You can change that
value to see the effect on the breaking of the content.

When things don\'t work as expected
-----------------------------------

If you have small amounts of content and are trying to control breaks on
several elements, your content needs to break somewhere, so you may not
always get the result you intended. To some extent, your use of
fragmentation is always a suggestion to the browser, to control breaks
in this way if it is possible. If the content doesn\'t break where you
intended, the result may be untidy, but the content is still available
for your users.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout/Handling_content_breaks_in_multicol_layout>

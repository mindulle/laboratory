Box alignment in multi-column layout
====================================

The [box alignment](css_box_alignment.md) specification details how
alignment works in various layout methods; on this page we explore how
Box Alignment works in the context of [](css_multicol_layout.md). As this page aims to detail things
which are specific to Multi-column Layout and Box Alignment, it should
be read in conjunction with the main [](css_box_alignment.md) page which details the common features
of Box Alignment across layout methods.

In multi-column layout the alignment container is the content box of the
multicol container. The alignment subject is the column box. The
properties which apply to multi-column layouts are detailed below.

**Note:** Multi-column layout predates the box alignment specification.
And the properties listed here, while specified for Multicol, may not be
supported in browsers.

align-content and justify-content
---------------------------------

The [`align-content`](align-content.md) property applies to the block
axis and [`justify-content`](justify-content.md) to the inline axis. Any
spacing added to the columns due to use of space distribution will be
added to the gap between the columns, therefore making the gap larger
than might be specified by the [`column-gap`](column-gap.md) property.

Using a value of `justify-content` other than `normal` or `stretch` will
cause column boxes to display at the [`column-width`](column-width.md)
specified on the multicol container, and the remaining space distributed
according to the value of justify-content.

column-gap
----------

The [`column-gap`](column-gap.md) property was specified in earlier
versions of the multiple-column layout specification, and has now been
unified with the gap properties for other layout methods in box
alignment. While other layout methods treat the initial value of
column-gap as 0 multicol treats it as 1em, as in general you would not
want to have no gap between columns.

Reference
---------

### CSS Properties

- [`justify-content`](justify-content.md)
- [`align-content`](align-content.md)
- [`column-gap`](column-gap.md)

### Glossary Entries

- [Alignment
    subject](https://developer.mozilla.org/en-US/docs/Glossary/Alignment_Subject)
- [Alignment
    container](https://developer.mozilla.org/en-US/docs/Glossary/Alignment_Container)
- [Fallback
    alignment](https://developer.mozilla.org/en-US/docs/Glossary/Fallback_Alignment)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_alignment/Box_alignment_in_multi-column_layout>

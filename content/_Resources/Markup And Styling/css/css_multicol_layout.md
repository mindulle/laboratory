CSS multi-column layout
=======================

The **CSS multi-column layout** module lets you divide content across
multiple columns. By using the properties in this module, you can define
the preferred number and width of columns, the gap size between columns,
and the visual appearance of the optional column dividing lines (known
as column rules). You can also define how content should flow from
column to column and how to break content between columns.

Multi-column layout in action
-----------------------------

In this example, the 1967 speech from Canada\'s centennial, *A Lament
for Confederation*, by Chief Dan George, is displayed across multiple
columns, similar to the way articles are displayed in printed
newspapers. If you have JavaScript enabled, controls enable changing the
preferred column number and width, the width of the gap between columns,
whether the title and a sample blockquote should be contained in a
single column or made to span all columns, and whether breaking within
the paragraphs should be avoided.

To see the code for this columned layout, [view the source on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/multicol.html).

**Note:** Multiple-column layout is closely related to [](css_paged_media.md). Each column box is a fragment, much like each
printed page is a fragment of a document. Using the properties defined
in the [CSS fragmentation](css_fragmentation.md) module, you can control
how content breaks between columns and pages.

Reference
---------

### Properties

- [`break-after`](break-after.md)
- [`break-before`](break-before.md)
- [`break-inside`](break-inside.md)
- [`column-fill`](column-fill.md)
- [`column-gap`](column-gap.md)
- [`column-span`](column-span.md)
- [`column-rule`](column-rule.md) shorthand
  - [`column-rule-color`](column-rule-color.md)
  - [`column-rule-style`](column-rule-style.md)
  - [`column-rule-width`](column-rule-width.md)
- [`columns`](columns.md) shorthand
  - [`column-count`](column-count.md)
  - [`column-width`](column-width.md)

**Note:** Bear in mind that setting container height and line length can
pose challenges for people with visual or cognitive disabilities. [WCAG
Success Criterion
1.4.8](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
states that even when the text size is doubled, content should not need
to be scrolled.

Guides
------

[Basic concepts of multi-column layout](_Resources/Markup%20And%20Styling/css/css_multicol_layout/basic_concepts.md)

:   An overview of the Multiple-column Layout specification

[Styling columns](styling_columns.md)

:   How to use column rules and manage the spacing between columns.

[Spanning and balancing](spanning_balancing_columns.md)

:   How to make elements span across all columns and control the way
    columns are filled.

[Handling overflow in multi-column layout](handling_overflow_in_multicol_layout.md)

:   What happens when an item overflows the column it is in and what
    happens when there is too much columned content to fit a container.

[Handling content breaks in multi-column layout](handling_content_breaks_in_multicol_layout.md)

:   Introduction to the Fragmentation specification and how to control
    where column content breaks.

Related concepts
----------------

- [`orphans`](orphans.md) CSS property
- [`widows`](widows.md) CSS property
- [`overflow`](overflow.md) CSS property
- [`gap`](gap.md) CSS property
- [`height`](_Resources/Markup%20And%20Styling/css/height.md), [`max-height`](max-height.md), and
    [`block-size`](block-size.md) CSS properties
- [`width`](_Resources/Markup%20And%20Styling/css/width.md), [`max-width`](max-width.md), and
    [`inline-size`](inline-size.md) CSS properties
- [`<line-style>`](line-style.md) enumerated data type
- [Block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
    guide

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  ](https://drafts.csswg.org/css-multicol/)

  -----------------------------------------------------------------------

See also
--------

- [Learn: multiple-column
    layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [CSS fragmentation](css_fragmentation.md) module
- [CSS flexible box layout](css_flexible_box_layout.md) module
- [CSS grid layout](css_grid_layout.md) module
- [CSS paged media](css_paged_media.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_multicol_layout>

CSS grid layout
===============

The **CSS grid layout** module excels at dividing a page into major
regions or defining the relationship in terms of size, position, and
layer, between parts of a control built from HTML primitives.

Like tables, grid layout enables an author to align elements into
columns and rows. However, many more layouts are either possible or
easier with CSS grid than they were with tables. For example, a grid
container\'s child elements could position themselves so they actually
overlap and layer, similar to CSS positioned elements.

Basic example
-------------

The example below shows a three-column track grid with new rows created
at a minimum of 100 pixels and a maximum of auto. Items have been placed
onto the grid using line-based placement.

### HTML

[html]

```html
<div class="wrapper">
  <div class="one">One</div>
  <div class="two">Two</div>
  <div class="three">Three</div>
  <div class="four">Four</div>
  <div class="five">Five</div>
  <div class="six">Six</div>
</div>
```

### CSS

[css]

```css
.wrapper {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
  grid-auto-rows: minmax(100px, auto);
}
.one {
  grid-column: 1 / 3;
  grid-row: 1;
}
.two {
  grid-column: 2 / 4;
  grid-row: 1 / 3;
}
.three {
  grid-column: 1;
  grid-row: 2 / 5;
}
.four {
  grid-column: 3;
  grid-row: 3;
}
.five {
  grid-column: 2;
  grid-row: 4;
}
.six {
  grid-column: 3;
  grid-row: 4;
}
```

Reference
---------

### Properties

- [`display`](display.md)
- [`grid-template-columns`](grid-template-columns.md)
- [`grid-template-rows`](grid-template-rows.md)
- [`grid-template-areas`](grid-template-areas.md)
- [`grid-template`](grid-template.md)
- [`grid-auto-columns`](grid-auto-columns.md)
- [`grid-auto-rows`](grid-auto-rows.md)
- [`grid-auto-flow`](grid-auto-flow.md)
- [`grid`](_Resources/Markup%20And%20Styling/css/grid.md)
- [`grid-row-start`](grid-row-start.md)
- [`grid-column-start`](grid-column-start.md)
- [`grid-row-end`](grid-row-end.md)
- [`grid-column-end`](grid-column-end.md)
- [`grid-row`](grid-row.md)
- [`grid-column`](grid-column.md)
- [`grid-area`](grid-area.md)
- [`row-gap`](row-gap.md)
- [`column-gap`](column-gap.md)
- [`gap`](gap.md)
- [`masonry-auto-flow`](masonry-auto-flow.md)
    [Experimental]
- [`align-tracks`](align-tracks.md) [Experimental]
- [`justify-tracks`](justify-tracks.md) [Experimental]

### Functions

- [`repeat()`](repeat.md)
- [`minmax()`](minmax.md)
- [`fit-content()`](fit-content_function.md)

### Data types

- [`<flex>`](flex_value.md)

Guides
------

- [](basic_concepts_of_grid_layout.md)
- [](relationship_of_grid_layout_with_other_layout_methods.md)
- [Grid template areas](grid_template_areas.md)
- [](grid_layout_using_line-based_placement.md)
- [](grid_layout_using_named_grid_lines.md)
- [](auto-placement_in_grid_layout.md)
- [](_Resources/Markup%20And%20Styling/css/css_grid_layout/box_alignment_in_grid_layout.md)
- [](grids_logical_values_and_writing_modes.md)
- [](grid_layout_and_accessibility.md)
- [](realizing_common_layouts_using_grids.md)
- [Subgrid](subgrid.md)
- [Masonry layout](masonry_layout.md)
    [Experimental]

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  ](https://drafts.csswg.org/css-grid/)

  -----------------------------------------------------------------------

See also
--------

- Glossary terms:
  - [Grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid)
  - [Grid
        lines](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Lines)
  - [Grid
        tracks](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Tracks)
  - [Grid
        cell](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Cell)
  - [Grid
        area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas)
  - [Gutters](https://developer.mozilla.org/en-US/docs/Glossary/Gutters)
  - [Grid
        axis](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Axis)
  - [Grid
        row](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Row)
  - [Grid
        column](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Column)
- [Grid by Example](https://gridbyexample.com/) - A collection of
    usage examples and video tutorials
- [CSS Grid Reference -
    Codrops](https://tympanus.net/codrops/css_reference/grid/)
- [CSS Grid Inspector - Firefox
    DevTools](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/examine_grid_layouts/index.html)
- [CSS Grid
    Playground](https://mozilladevelopers.github.io/playground/css-grid/)
- [CSS Grid Garden](https://cssgridgarden.com) - A game for learning
    CSS grid

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout>

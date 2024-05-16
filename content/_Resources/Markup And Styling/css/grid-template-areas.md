grid-template-areas
===================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `grid-template-areas` CSS property specifies named [grid
areas](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas),
establishing the cells in the grid and assigning them names.

Try it
------

Those areas are not associated with any particular grid item, but can be
referenced from the grid-placement properties
[`grid-row-start`](grid-row-start.md), [`grid-row-end`](grid-row-end.md),
[`grid-column-start`](grid-column-start.md),
[`grid-column-end`](grid-column-end.md), and their shorthands
[`grid-row`](grid-row.md), [`grid-column`](grid-column.md), and
[`grid-area`](grid-area.md).

Syntax
------

[css]

```css
/* Keyword value */
grid-template-areas: none;

/* <string> values */
grid-template-areas: "a b";
grid-template-areas:
  "a b b"
  "a c d";

/* Global values */
grid-template-areas: inherit;
grid-template-areas: initial;
grid-template-areas: revert;
grid-template-areas: revert-layer;
grid-template-areas: unset;
```

### Values

[`none`](#none)

:   The grid container doesn\'t define any named grid areas.

`<string>`+

:   A row is created for every separate string listed, and a column is
    created for each cell in the string. Multiple cell tokens with the
    same name within and between rows create a single named grid area
    that spans the corresponding grid cells. Unless those cells form a
    rectangle, the declaration is invalid.

Formal definition
-----------------

  ---------------------------------- -----------------
  [Initial value](initial_value.md)     `none`
  Applies to                         grid containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------

Formal syntax
-------------

```
grid-template-areas = 
  none       |
  <string>+  
```

Examples
--------

### Specifying named grid areas

#### HTML

[html]

```html
<section id="page">
  <header>Header</header>
  <nav>Navigation</nav>
  <main>Main area</main>
  <footer>Footer</footer>
</section>
```

#### CSS

[css]

```css
#page {
  display: grid;
  width: 100%;
  height: 250px;
  grid-template-areas:
    "head head"
    "nav  main"
    "nav  foot";
  grid-template-rows: 50px 1fr 30px;
  grid-template-columns: 150px 1fr;
}

#page > header {
  grid-area: head;
  background-color: #8ca0ff;
}

#page > nav {
  grid-area: nav;
  background-color: #ffa08c;
}

#page > main {
  grid-area: main;
  background-color: #ffff64;
}

#page > footer {
  grid-area: foot;
  background-color: #8cffa0;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  grid-template-areas-property]](https://drafts.csswg.org/css-grid/#grid-template-areas-property)

  ---------------------------------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`grid-template-areas`

57

16

52

No

44

10.1

57

57

52

43

10.3

6.0

See also
--------

- Related CSS properties: [`grid-template-rows`](grid-template-rows.md),
    [`grid-template-columns`](grid-template-columns.md),
    [`grid-template`](grid-template.md)
- Grid Layout Guide: *[](grid_template_areas.md)*
- Video tutorial: *[Grid Template
    Areas](https://gridbyexample.com/video/grid-template-areas/)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas>

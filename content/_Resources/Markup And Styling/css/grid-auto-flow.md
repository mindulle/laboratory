grid-auto-flow
==============

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `grid-auto-flow` CSS property controls how the auto-placement
algorithm works, specifying exactly how auto-placed items get flowed
into the grid.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
grid-auto-flow: row;
grid-auto-flow: column;
grid-auto-flow: dense;
grid-auto-flow: row dense;
grid-auto-flow: column dense;

/* Global values */
grid-auto-flow: inherit;
grid-auto-flow: initial;
grid-auto-flow: revert;
grid-auto-flow: revert-layer;
grid-auto-flow: unset;
```

This property may take one of two forms:

- a single keyword: one of `row`, `column`, or `dense`.
- two keywords: `row dense` or `column dense`.

### Values

[`row`](#row)

:   Items are placed by filling each row in turn, adding new rows as
    necessary. If neither `row` nor `column` is provided, `row` is
    assumed.

[`column`](#column)

:   Items are placed by filling each column in turn, adding new columns
    as necessary.

[`dense`](#dense)

:   \"dense\" packing algorithm attempts to fill in holes earlier in the
    grid, if smaller items come up later. This may cause items to appear
    out-of-order, when doing so would fill in holes left by larger
    items.

    If it is omitted, a \"sparse\" algorithm is used, where the
    placement algorithm only ever moves \"forward\" in the grid when
    placing items, never backtracking to fill holes. This ensures that
    all of the auto-placed items appear \"in order\", even if this
    leaves holes that could have been filled by later items.

Formal definition
-----------------

  ---------------------------------- -----------------
  [Initial value](initial_value.md)     `row`
  Applies to                         grid containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------

Formal syntax
-------------

```
grid-auto-flow = 
  [ row | column ]  ||
  dense             
```

Examples
--------

### Setting grid auto-placement

#### HTML

[html]

```html
<div id="grid">
  <div id="item1"></div>
  <div id="item2"></div>
  <div id="item3"></div>
  <div id="item4"></div>
  <div id="item5"></div>
</div>
<select id="direction">
  <option value="column">column</option>
  <option value="row">row</option>
</select>
<input id="dense" type="checkbox" />
<label for="dense">dense</label>
```

#### CSS

[css]

```css
#grid {
  height: 200px;
  width: 200px;
  display: grid;
  gap: 10px;
  grid-template: repeat(4, 1fr) / repeat(2, 1fr);
  grid-auto-flow: column; /* or 'row', 'row dense', 'column dense' */
}

#item1 {
  background-color: lime;
  grid-row-start: 3;
}

#item2 {
  background-color: yellow;
}

#item3 {
  background-color: blue;
}

#item4 {
  grid-column-start: 2;
  background-color: red;
}

#item5 {
  background-color: aqua;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  grid-auto-flow-property]](https://drafts.csswg.org/css-grid/#grid-auto-flow-property)

  -----------------------------------------------------------------------------------------------

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

`grid-auto-flow`

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

- Related CSS properties: [`grid-auto-rows`](grid-auto-rows.md),
    [`grid-auto-columns`](grid-auto-columns.md), [`grid`](_Resources/Markup%20And%20Styling/css/grid.md)
- Grid Layout Guide: *[](auto-placement_in_grid_layout.md)*
- Video tutorial: *[Introducing Grid auto-placement and
    order](https://gridbyexample.com/video/series-auto-placement-order/)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-flow>

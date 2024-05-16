table-layout
============

The `table-layout` CSS property sets the algorithm used to lay out
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
cells, rows, and columns.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
table-layout: auto;
table-layout: fixed;

/* Global values */
table-layout: inherit;
table-layout: initial;
table-layout: revert;
table-layout: revert-layer;
table-layout: unset;
```

### Values

[`auto`](#auto)

:   The automatic table layout algorithm is used. The widths of the
    table and its cells are adjusted to fit the content. Most browsers
    use this algorithm by default.

[`fixed`](#fixed)

:   The fixed table layout algorithm is used. When using this keyword,
    the table\'s width *needs to be specified explicitly* using the
    [`width`](_Resources/Markup%20And%20Styling/css/width.md) property. If the value of the `width` property is
    set to `auto`or is not specified, the browser uses the automatic
    table layout algorithm, in which case the `fixed` value has no
    effect.\
    The fixed table layout algorithm is faster than the automatic layout
    algorithm because the horizontal layout of the table depends only on
    the table\'s width, the width of the columns, and borders or cell
    spacing. The horizontal layout doesn\'t depend on the contents of
    the cells because it depends only on explicitly set widths.

    In the fixed table layout algorithm, the width of each column is
    determined as follows:

    -   A column element with explicit width sets the width for that
        column.
    -   Otherwise, a cell in the first row with explicit width
        determines the width for that column.
    -   Otherwise, the column gets the width from the shared remaining
        horizontal space.

    With this algorithm the entire table can be rendered once the first
    table row has been downloaded and analyzed. This can speed up
    rendering time over the \"automatic\" layout method, but subsequent
    cell content might not fit in the column widths provided. Cells use
    the [`overflow`](overflow) property to determine whether to clip any
    overflowing content, but only if the table has a known width;
    otherwise, they won\'t overflow the cells.

Formal definition
-----------------

  ---------------------------------- -------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         `table` and `inline-table` elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -------------------------------------

Formal syntax
-------------

```
table-layout = 
  auto   |
  fixed  
```

Examples
--------

### Fixed-width tables with text-overflow

This example uses a fixed table layout, combined with the
[`width`](_Resources/Markup%20And%20Styling/css/width.md) property, to restrict the table\'s width. The
[`text-overflow`](text-overflow.md) property is used to apply an ellipsis
to words that are too long to fit. If the table layout were `auto`, the
table would grow to accommodate its contents, despite the specified
`width`.

#### HTML

[html]

```html
<table>
  <tr>
    <td>Ed</td>
    <td>Wood</td>
  </tr>
  <tr>
    <td>Albert</td>
    <td>Schweitzer</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Fonda</td>
  </tr>
  <tr>
    <td>William</td>
    <td>Shakespeare</td>
  </tr>
</table>
```

#### CSS

[css]

```css
table {
  table-layout: fixed;
  width: 120px;
  border: 1px solid red;
}

td {
  border: 1px solid blue;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\# width-layout]](https://drafts.csswg.org/css2/#width-layout)

  -----------------------------------------------------------------------

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

`table-layout`

14

12

1

5

7

1

1.5

18

4

10.1

3

1.0

See also
--------

- [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/table-layout>

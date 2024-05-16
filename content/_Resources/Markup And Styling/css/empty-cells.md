empty-cells
===========

The `empty-cells` CSS property sets whether borders and backgrounds
appear around
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
cells that have no visible content.

Try it
------

This property has an effect only when the
[`border-collapse`](border-collapse.md) property is `separate`.

Syntax
------

[css]

```css
/* Keyword values */
empty-cells: show;
empty-cells: hide;

/* Global values */
empty-cells: inherit;
empty-cells: initial;
empty-cells: revert;
empty-cells: revert-layer;
empty-cells: unset;
```

The `empty-cells` property is specified as one of the keyword values
listed below.

### Values

[`show`](#show)

:   Borders and backgrounds are drawn like in normal cells.

[`hide`](#hide)

:   No borders or backgrounds are drawn.

Formal definition
-----------------

  ---------------------------------- ---------------------
  [Initial value](initial_value.md)     `show`
  Applies to                         table-cell elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------

Formal syntax
-------------

```
empty-cells = 
  show  |
  hide  
```

Examples
--------

### Showing and hiding empty table cells

#### HTML

[html]

```html
<table class="table_1">
  <tr>
    <td>Moe</td>
    <td>Larry</td>
  </tr>
  <tr>
    <td>Curly</td>
    <td></td>
  </tr>
</table>
<br />
<table class="table_2">
  <tr>
    <td>Moe</td>
    <td>Larry</td>
  </tr>
  <tr>
    <td>Curly</td>
    <td></td>
  </tr>
</table>
```

#### CSS

[css]

```css
.table_1 {
  empty-cells: show;
}

.table_2 {
  empty-cells: hide;
}

td,
th {
  border: 1px solid gray;
  padding: 0.5rem;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\# empty-cells]](https://drafts.csswg.org/css2/#empty-cells)

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

`empty-cells`

1

12

1

8

4

1.2

4.4

18

4

10.1

1

1.0

See also
--------

- [`border-collapse`](border-collapse.md)
- [Styling
    tables](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Styling_tables)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/empty-cells>

border-spacing
==============

The `border-spacing`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the distance between the borders of adjacent cells in a
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).
This property applies only when [`border-collapse`](border-collapse.md) is
`separate`.

Try it
------

The `border-spacing` value is also used along the outside edge of the
table, where the distance between the table\'s border and the cells in
the first/last column or row is the sum of the relevant (horizontal or
vertical) `border-spacing` and the relevant (top, right, bottom, or
left) [`padding`](padding.md) on the table.

**Note:** The `border-spacing` property is equivalent to the deprecated
`cellspacing` attribute of the `<table>` element, except that
`border-spacing` has an optional second value that can be used to set
different horizontal and vertical spacing.

Syntax
------

[css]

```css
/* <length> */
border-spacing: 2px;

/* horizontal <length> | vertical <length> */
border-spacing: 1cm 2em;

/* Global values */
border-spacing: inherit;
border-spacing: initial;
border-spacing: revert;
border-spacing: revert-layer;
border-spacing: unset;
```

The `border-spacing` property may be specified as either one or two
values.

- When **one** `<length>` value is specified, it defines both the
    horizontal and vertical spacings between cells.
- When **two** `<length>` values are specified, the first value
    defines the horizontal spacing between cells (i.e., the space
    between cells in adjacent *columns*), and the second value defines
    the vertical spacing between cells (i.e., the space between cells in
    adjacent *rows*).

### Values

[`<length>`](length.md)

:   The size of the spacing as a fixed value.

Formal definition
-----------------

  ---------------------------------- -------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         `table` and `inline-table` elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   two absolute lengths
  Animation type                     discrete
  ---------------------------------- -------------------------------------

Formal syntax
-------------

```
border-spacing = 
  <length>  
```

Examples
--------

### Spacing and padding table cells

This example applies a spacing of `.5em` vertically and `1em`
horizontally between a table\'s cells. Note how, along its outside
edges, the table\'s `padding` values are added to its `border-spacing`
values.

#### HTML

[html]

```html
<table>
  <tr>
    <td>1</td>
    <td>2</td>
    <td>3</td>
  </tr>
  <tr>
    <td>4</td>
    <td>5</td>
    <td>6</td>
  </tr>
  <tr>
    <td>7</td>
    <td>8</td>
    <td>9</td>
  </tr>
</table>
```

#### CSS

[css]

```css
table {
  border-spacing: 1em 0.5em;
  padding: 0 2em 1em 0;
  border: 1px solid orange;
}

td {
  width: 1.5em;
  height: 1.5em;
  background: #d2d2d2;
  text-align: center;
  vertical-align: middle;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  separated-borders]](https://drafts.csswg.org/css2/#separated-borders)

  -------------------------------------------------------------------------------

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

`border-spacing`

1

12

1

8

4

1

≤37

18

4

14

1

1.0

See also
--------

- [`border-collapse`](border-collapse.md), [`border-style`](border-style.md)
- The `border-spacing` property alters the appearance of the
    [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
    HTML element.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing>

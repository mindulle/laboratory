border-collapse
===============

The `border-collapse`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether cells inside a
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
have shared or separate borders.

Try it
------

When cells are collapsed, the [`border-style`](border-style.md) value of
`inset` behaves like `ridge`, and `outset` behaves like `groove`.

When cells are separated, the distance between cells is defined by the
[`border-spacing`](border-spacing.md) property.

Syntax
------

[css]

```css
/* Keyword values */
border-collapse: collapse;
border-collapse: separate;

/* Global values */
border-collapse: inherit;
border-collapse: initial;
border-collapse: revert;
border-collapse: revert-layer;
border-collapse: unset;
```

The `border-collapse` property is specified as a single keyword, which
may be chosen from the list below.

### Values

[`collapse`](#collapse)

:   Adjacent cells have shared borders (the collapsed-border table
    rendering model).

[`separate`](#separate)

:   Adjacent cells have distinct borders (the separated-border table
    rendering model).

Formal definition
-----------------

  ---------------------------------- -------------------------------------
  [Initial value](initial_value.md)     `separate`
  Applies to                         `table` and `inline-table` elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -------------------------------------

Formal syntax
-------------

```
border-collapse = 
  separate  |
  collapse  
```

Examples
--------

### A colorful table of browser engines

#### HTML

[html]

```html
<table class="separate">
  <caption>
    <code>border-collapse: separate</code>
  </caption>
  <tbody>
    <tr>
      <th>Browser</th>
      <th>Layout Engine</th>
    </tr>
    <tr>
      <td class="fx">Firefox</td>
      <td class="gk">Gecko</td>
    </tr>
    <tr>
      <td class="ed">Edge</td>
      <td class="tr">EdgeHTML</td>
    </tr>
    <tr>
      <td class="sa">Safari</td>
      <td class="wk">Webkit</td>
    </tr>
    <tr>
      <td class="ch">Chrome</td>
      <td class="bk">Blink</td>
    </tr>
    <tr>
      <td class="op">Opera</td>
      <td class="bk">Blink</td>
    </tr>
  </tbody>
</table>
<table class="collapse">
  <caption>
    <code>border-collapse: collapse</code>
  </caption>
  <tbody>
    <tr>
      <th>Browser</th>
      <th>Layout Engine</th>
    </tr>
    <tr>
      <td class="fx">Firefox</td>
      <td class="gk">Gecko</td>
    </tr>
    <tr>
      <td class="ed">Edge</td>
      <td class="tr">EdgeHTML</td>
    </tr>
    <tr>
      <td class="sa">Safari</td>
      <td class="wk">Webkit</td>
    </tr>
    <tr>
      <td class="ch">Chrome</td>
      <td class="bk">Blink</td>
    </tr>
    <tr>
      <td class="op">Opera</td>
      <td class="bk">Blink</td>
    </tr>
  </tbody>
</table>
```

#### CSS

[css]

```css
.collapse {
  border-collapse: collapse;
}

.separate {
  border-collapse: separate;
}

table {
  display: inline-table;
  margin: 1em;
  border: dashed 5px;
}

table th,
table td {
  border: solid 3px;
}

.fx {
  border-color: orange blue;
}
.gk {
  border-color: black red;
}
.ed {
  border-color: blue gold;
}
.tr {
  border-color: aqua;
}
.sa {
  border-color: silver blue;
}
.wk {
  border-color: gold blue;
}
.ch {
  border-color: red yellow green blue;
}
.bk {
  border-color: navy blue teal aqua;
}
.op {
  border-color: red;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  propdef-border-collapse]](https://drafts.csswg.org/css2/#propdef-border-collapse)

  -------------------------------------------------------------------------------------------

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

`border-collapse`

1

12

1

5

4

1.2

2.2

18

4

10.1

3

1.0

See also
--------

- [`border-spacing`](border-spacing.md), [`border-style`](border-style.md)
- The `border-collapse` property alters the appearance of the
    [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
    HTML element.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse>

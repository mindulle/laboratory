border-bottom-style
===================

The `border-bottom-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the line style of an element\'s bottom [`border`](border.md).

Try it
------

**Note:** The specification doesn\'t define how borders of different
styles connect in the corners.

Syntax
------

[css]

```css
/* Keyword values */
border-bottom-style: none;
border-bottom-style: hidden;
border-bottom-style: dotted;
border-bottom-style: dashed;
border-bottom-style: solid;
border-bottom-style: double;
border-bottom-style: groove;
border-bottom-style: ridge;
border-bottom-style: inset;
border-bottom-style: outset;

/* Global values */
border-bottom-style: inherit;
border-bottom-style: initial;
border-bottom-style: revert;
border-bottom-style: revert-layer;
border-bottom-style: unset;
```

The `border-bottom-style` property is specified as a single
[`<line-style>`](line-style.md) keyword value.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------

Formal syntax
-------------

```
border-bottom-style = 
  <line-style>  

<line-style> = 
  none    |
  hidden  |
  dotted  |
  dashed  |
  solid   |
  double  |
  groove  |
  ridge   |
  inset   |
  outset  
```

Examples
--------

### Demonstrating all border styles

#### HTML

[html]

```html
<table>
  <tr>
    <td class="b1">none</td>
    <td class="b2">hidden</td>
    <td class="b3">dotted</td>
    <td class="b4">dashed</td>
  </tr>
  <tr>
    <td class="b5">solid</td>
    <td class="b6">double</td>
    <td class="b7">groove</td>
    <td class="b8">ridge</td>
  </tr>
  <tr>
    <td class="b9">inset</td>
    <td class="b10">outset</td>
  </tr>
</table>
```

#### CSS

[css]

```css
/* Define look of the table */
table {
  border-width: 3px;
  background-color: #52e385;
}
tr,
td {
  padding: 3px;
}

/* border-bottom-style example classes */
.b1 {
  border-bottom-style: none;
}
.b2 {
  border-bottom-style: hidden;
}
.b3 {
  border-bottom-style: dotted;
}
.b4 {
  border-bottom-style: dashed;
}
.b5 {
  border-bottom-style: solid;
}
.b6 {
  border-bottom-style: double;
}
.b7 {
  border-bottom-style: groove;
}
.b8 {
  border-bottom-style: ridge;
}
.b9 {
  border-bottom-style: inset;
}
.b10 {
  border-bottom-style: outset;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  border-style]](https://drafts.csswg.org/css-backgrounds/#border-style)

  --------------------------------------------------------------------------------

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

`border-bottom-style`

1

12

1Before Firefox 50, border styles of rounded corners (with
[`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius))
were always rendered as if `border-bottom-style` was `solid`. This has
been fixed in Firefox 50.

5.5

9.2

1

≤37

18

4Before Firefox 50, border styles of rounded corners (with
[`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius))
were always rendered as if `border-bottom-style` was `solid`. This has
been fixed in Firefox 50.

14

1

1.0

See also
--------

- The other style-related border properties:
    [`border-left-style`](border-left-style.md),
    [`border-right-style`](border-right-style.md),
    [`border-top-style`](border-top-style.md), and
    [`border-style`](border-style.md).
- The other bottom-border-related properties:
    [`border-bottom`](border-bottom.md),
    [`border-bottom-color`](border-bottom-color.md), and
    [`border-bottom-width`](border-bottom-width.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-style>

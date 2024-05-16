border-right-style
==================

The `border-right-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the line style of an element\'s right [`border`](border.md).

Try it
------

**Note:** The specification doesn\'t define how borders of different
styles connect in the corners.

Syntax
------

[css]

```css
/* Keyword values */
border-right-style: none;
border-right-style: hidden;
border-right-style: dotted;
border-right-style: dashed;
border-right-style: solid;
border-right-style: double;
border-right-style: groove;
border-right-style: ridge;
border-right-style: inset;
border-right-style: outset;

/* Global values */
border-right-style: inherit;
border-right-style: initial;
border-right-style: revert;
border-right-style: revert-layer;
border-right-style: unset;
```

The `border-right-style` property is specified as a single
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
border-right-style = 
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

### Border styles

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
  border-width: 2px;
  background-color: #52e385;
}
tr,
td {
  padding: 3px;
}

/* border-right-style example classes */
.b1 {
  border-right-style: none;
}
.b2 {
  border-right-style: hidden;
}
.b3 {
  border-right-style: dotted;
}
.b4 {
  border-right-style: dashed;
}
.b5 {
  border-right-style: solid;
}
.b6 {
  border-right-style: double;
}
.b7 {
  border-right-style: groove;
}
.b8 {
  border-right-style: ridge;
}
.b9 {
  border-right-style: inset;
}
.b10 {
  border-right-style: outset;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-style]](https://drafts.csswg.org/css-backgrounds/#the-border-style)

  ----------------------------------------------------------------------------------------

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

`border-right-style`

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

14Before Firefox 50, border styles of rounded corners (with
[`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius))
were always rendered as if `border-bottom-style` was `solid`. This has
been fixed in Firefox 50.

14

1

1.0

See also
--------

- The other style-related border properties:
    [`border-bottom-style`](border-bottom-style.md),
    [`border-left-style`](border-left-style.md),
    [`border-top-style`](border-top-style.md), and
    [`border-style`](border-style.md).
- The other right-border-related properties:
    [`border-right`](border-right.md),
    [`border-right-color`](border-right-color.md), and
    [`border-right-width`](border-right-width.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-style>

border-top-style
================

The `border-top-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the line style of an element\'s top [`border`](border.md).

Try it
------

**Note:** The specification doesn\'t define how borders of different
styles connect in the corners.

Syntax
------

[css]

```css
/* Keyword values */
border-top-style: none;
border-top-style: hidden;
border-top-style: dotted;
border-top-style: dashed;
border-top-style: solid;
border-top-style: double;
border-top-style: groove;
border-top-style: ridge;
border-top-style: inset;
border-top-style: outset;

/* Global values */
border-top-style: inherit;
border-top-style: initial;
border-top-style: revert;
border-top-style: revert-layer;
border-top-style: unset;
```

The `border-top-style` property is specified as a single
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
border-top-style = 
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

### Setting border-top-style

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

/* border-top-style example classes */
.b1 {
  border-top-style: none;
}
.b2 {
  border-top-style: hidden;
}
.b3 {
  border-top-style: dotted;
}
.b4 {
  border-top-style: dashed;
}
.b5 {
  border-top-style: solid;
}
.b6 {
  border-top-style: double;
}
.b7 {
  border-top-style: groove;
}
.b8 {
  border-top-style: ridge;
}
.b9 {
  border-top-style: inset;
}
.b10 {
  border-top-style: outset;
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

`border-top-style`

1

12

1Before Firefox 50, border styles of rounded corners (with
[`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius))
were always rendered as if `border-top-style` was `solid`. This has been
fixed in Firefox 50.

5.5

9.2

1

≤37

18

4Before Firefox 50, border styles of rounded corners (with
[`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius))
were always rendered as if `border-top-style` was `solid`. This has been
fixed in Firefox 50.

14

1

1.0

See also
--------

- The other style-related border properties:
    [`border-left-style`](border-left-style.md),
    [`border-right-style`](border-right-style.md),
    [`border-bottom-style`](border-bottom-style.md), and
    [`border-style`](border-style.md).
- The other top-border-related properties: [`border-top`](border-top.md),
    [`border-top-color`](border-top-color.md), and
    [`border-top-width`](border-top-width.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-top-style>

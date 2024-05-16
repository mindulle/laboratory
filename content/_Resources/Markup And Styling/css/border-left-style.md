border-left-style
=================

The `border-left-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the line style of an element\'s left [`border`](border.md).

Try it
------

**Note:** The specification doesn\'t define how borders of different
styles connect in the corners.

Syntax
------

[css]

```css
/* Keyword values */
border-left-style: none;
border-left-style: hidden;
border-left-style: dotted;
border-left-style: dashed;
border-left-style: solid;
border-left-style: double;
border-left-style: groove;
border-left-style: ridge;
border-left-style: inset;
border-left-style: outset;

/* Global values */
border-left-style: inherit;
border-left-style: initial;
border-left-style: revert;
border-left-style: revert-layer;
border-left-style: unset;
```

The `border-left-style` property is specified as a single
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
border-left-style = 
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

### Setting border-left-style

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

/* border-left-style example classes */
.b1 {
  border-left-style: none;
}
.b2 {
  border-left-style: hidden;
}
.b3 {
  border-left-style: dotted;
}
.b4 {
  border-left-style: dashed;
}
.b5 {
  border-left-style: solid;
}
.b6 {
  border-left-style: double;
}
.b7 {
  border-left-style: groove;
}
.b8 {
  border-left-style: ridge;
}
.b9 {
  border-left-style: inset;
}
.b10 {
  border-left-style: outset;
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

`border-left-style`

1

12

1Before Firefox 50, border styles of rounded corners (with
[`border-radius`](https://developer.mozilla.org/docs/Web/CSS/border-radius))
were always rendered as if `border-bottom-style` was `solid`. This has
been fixed in Firefox 50.

5.5

9.2

1

2.2

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
    [`border-right-style`](border-right-style.md),
    [`border-top-style`](border-top-style.md), and
    [`border-style`](border-style.md).
- The other left-border-related properties:
    [`border-left`](border-left.md),
    [`border-left-color`](border-left-color.md), and
    [`border-left-width`](border-left-width.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-left-style>

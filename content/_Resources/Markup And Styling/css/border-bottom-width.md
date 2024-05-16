border-bottom-width
===================

The `border-bottom-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width of the bottom border of an element.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
border-bottom-width: thin;
border-bottom-width: medium;
border-bottom-width: thick;

/* <length> values */
border-bottom-width: 10em;
border-bottom-width: 3vmax;
border-bottom-width: 6px;

/* Global keywords */
border-bottom-width: inherit;
border-bottom-width: initial;
border-bottom-width: revert;
border-bottom-width: revert-layer;
border-bottom-width: unset;
```

### Values

[`<line-width>`](#line-width)

:   Defines the width of the border, either as an explicit nonnegative
    [`<length>`](length.md) or a keyword. If it\'s a keyword, it must be
    one of the following values:

    -   `thin`
    -   `medium`
    -   `thick`

**Note:** Because the specification doesn\'t define the exact thickness
denoted by each keyword, the precise result when using one of them is
implementation-specific. Nevertheless, they always follow the pattern
`thin ≤ medium ≤ thick`, and the values are constant within a single
document.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `medium`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   the absolute length or `0` if [`border-bottom-style`](border-bottom-style.md) is `none` or `hidden`
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-bottom-width = 
  <line-width>  

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           
```

Examples
--------

### Comparing bottom border widths

#### HTML

[html]

```html
<div>Element 1</div>
<div>Element 2</div>
```

#### CSS

[css]

```css
div {
  border: 1px solid red;
  margin: 1em 0;
}

div:nth-child(1) {
  border-bottom-width: thick;
}
div:nth-child(2) {
  border-bottom-width: 2em;
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
  the-border-width]](https://drafts.csswg.org/css-backgrounds/#the-border-width)

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

`border-bottom-width`

1

12

1

4

3.5

1

2.2

18

4

10.1

1

1.0

See also
--------

- The other border-width-related CSS properties:
    [`border-left-width`](border-left-width.md),
    [`border-right-width`](border-right-width.md),
    [`border-top-width`](border-top-width.md), and
    [`border-width`](border-width.md).
- The other border-bottom-related CSS properties: [`border`](border.md),
    [`border-bottom`](border-bottom.md),
    [`border-bottom-style`](border-bottom-style.md), and
    [`border-bottom-color`](border-bottom-color.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom-width>

border-right-width
==================

The `border-right-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width of the right border of an element.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
border-right-width: thin;
border-right-width: medium;
border-right-width: thick;

/* <length> values */
border-right-width: 10em;
border-right-width: 3vmax;
border-right-width: 6px;

/* Global keywords */
border-right-width: inherit;
border-right-width: initial;
border-right-width: revert;
border-right-width: revert-layer;
border-right-width: unset;
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

  ---------------------------------- ------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `medium`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   the absolute length or `0` if [`border-right-style`](border-right-style.md) is `none` or `hidden`
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-right-width = 
  <line-width>  

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           
```

Examples
--------

### Comparing border widths

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
  border-right-width: thick;
}
div:nth-child(2) {
  border-right-width: 2em;
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

`border-right-width`

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
    [`border-bottom-width`](border-bottom-width.md),
    [`border-left-width`](border-left-width.md),
    [`border-top-width`](border-top-width.md), and
    [`border-width`](border-width.md).
- The other border-right-related CSS properties: [`border`](border.md),
    [`border-right`](border-right.md),
    [`border-right-style`](border-right-style.md), and
    [`border-right-color`](border-right-color.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-right-width>

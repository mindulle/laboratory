border-width
============

The `border-width` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width of an element\'s border.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-bottom-width`](border-bottom-width.md)
- [`border-left-width`](border-left-width.md)
- [`border-right-width`](border-right-width.md)
- [`border-top-width`](border-top-width.md)

Syntax
------

[css]

```css
/* Keyword values */
border-width: thin;
border-width: medium;
border-width: thick;

/* <length> values */
border-width: 4px;
border-width: 1.2rem;

/* top and bottom | left and right */
border-width: 2px 1.5em;

/* top | left and right | bottom */
border-width: 1px 2em 1.5cm;

/* top | right | bottom | left */
border-width: 1px 2em 0 4rem;

/* Global values */
border-width: inherit;
border-width: initial;
border-width: revert;
border-width: revert-layer;
border-width: unset;
```

The `border-width` property may be specified using one, two, three, or
four values.

- When **one** value is specified, it applies the same width to **all
    four sides**.
- When **two** values are specified, the first width applies to the
    **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first width applies to the
    **top**, the second to the **left and right**, the third to the
    **bottom**.
- When **four** values are specified, the widths apply to the **top**,
    **right**, **bottom**, and **left** in that order (clockwise).

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

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-top-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-right-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-bottom-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-left-width.md): |
|                                   |     `medium`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements. It also applies to  |
|                                   | [`|
|                                   | ::first-letter`](::first-letter). |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-bottom-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-bottom-style.md) |
|                                   |     is `none` or `hidden`         |
|                                   | -   [](border-left-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-left-style.md) |
|                                   |     is `none` or `hidden`         |
|                                   | -   [](border-right-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-right-style.md) |
|                                   |     is `none` or `hidden`         |
|                                   | -   [](border-top-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-top-style.md) |
|                                   |     is `none` or `hidden`         |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-bottom-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
|                                   | -   [](border-left-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
|                                   | -   [](border-right-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
|                                   | -   [](border-top-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-width = 
  <line-width>  

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           
```

Examples
--------

### A mix of values and lengths

#### HTML

[html]

```html
<p id="one-value">one value: 6px wide border on all 4 sides</p>
<p id="two-values">
  two different values: 2px wide top and bottom border, 10px wide right and left
  border
</p>
<p id="three-values">
  three different values: 0.3em top, 9px bottom, and zero width right and left
</p>
<p id="four-values">
  four different values: "thin" top, "medium" right, "thick" bottom, and 1em
  left
</p>
```

#### CSS

[css]

```css
#one-value {
  border: ridge #ccc;
  border-width: 6px;
}
#two-values {
  border: solid red;
  border-width: 2px 10px;
}
#three-values {
  border: dotted orange;
  border-width: 0.3em 0 9px;
}
#four-values {
  border: solid lightgreen;
  border-width: thin medium thick 1em;
}
p {
  width: auto;
  margin: 0.25em;
  padding: 0.25em;
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

`border-width`

1

12

1

4

3.5

1

2

18

4

10.1

3

1.0

See also
--------

- The border-related shorthand properties: [`border`](border.md),
    [`border-style`](border-style.md), [`border-color`](border-color.md)
- The border-width-related properties:
    [`border-bottom-width`](border-bottom-width.md),
    [`border-left-width`](border-left-width.md),
    [`border-right-width`](border-right-width.md),
    [`border-top-width`](border-top-width.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-width>

border-color
============

The `border-color` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the color of an element\'s border.

Try it
------

Each side can be set individually using
[`border-top-color`](border-top-color.md),
[`border-right-color`](border-right-color.md),
[`border-bottom-color`](border-bottom-color.md), and
[`border-left-color`](border-left-color.md); or using the writing
mode-aware [`border-block-start-color`](border-block-start-color.md),
[`border-block-end-color`](border-block-end-color.md),
[`border-inline-start-color`](border-inline-start-color.md), and
[`border-inline-end-color`](border-inline-end-color.md).

You can find more information about border colors in [](applying_color.md#borders_2).

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-bottom-color`](border-bottom-color.md)
- [`border-left-color`](border-left-color.md)
- [`border-right-color`](border-right-color.md)
- [`border-top-color`](border-top-color.md)

Syntax
------

[css]

```css
/* <color> values */
border-color: red;

/* top and bottom | left and right */
border-color: red #f015ca;

/* top | left and right | bottom */
border-color: red rgb(240, 30, 50, 0.7) green;

/* top | right | bottom | left */
border-color: red yellow green blue;

/* Global values */
border-color: inherit;
border-color: initial;
border-color: revert;
border-color: revert-layer;
border-color: unset;
```

The `border-color` property may be specified using one, two, three, or
four values.

- When **one** value is specified, it applies the same color to **all
    four sides**.
- When **two** values are specified, the first color applies to the
    **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first color applies to the
    **top**, the second to the **left and right**, the third to the
    **bottom**.
- When **four** values are specified, the colors apply to the **top**,
    **right**, **bottom**, and **left** in that order (clockwise).

### Values

[`<color>`](color_value.md)

:   Defines the color of the border.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-top-color.md): |
|                                   |     `currentcolor`                |
|                                   | -   [](border-right-color.md): |
|                                   |     `currentcolor`                |
|                                   | -   [](border-bottom-color.md): |
|                                   |     `currentcolor`                |
|                                   | -   [](border-left-color.md): |
|                                   |     `currentcolor`                |
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
|                                   | -   [](border-bottom-color.md): |
|                                   |     computed color                |
|                                   | -   [](border-left-color.md): |
|                                   |     computed color                |
|                                   | -   [](border-right-color.md): |
|                                   |     computed color                |
|                                   | -   [](border-top-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-bottom-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](border-left-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](border-right-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](border-top-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-color = 
  <color>  
```

Examples
--------

### Complete border-color usage

#### HTML

[html]

```html
<div id="justone">
  <p><code>border-color: red;</code> is equivalent to</p>
  <ul>
    <li><code>border-top-color: red;</code></li>
    <li><code>border-right-color: red;</code></li>
    <li><code>border-bottom-color: red;</code></li>
    <li><code>border-left-color: red;</code></li>
  </ul>
</div>
<div id="horzvert">
  <p><code>border-color: gold red;</code> is equivalent to</p>
  <ul>
    <li><code>border-top-color: gold;</code></li>
    <li><code>border-right-color: red;</code></li>
    <li><code>border-bottom-color: gold;</code></li>
    <li><code>border-left-color: red;</code></li>
  </ul>
</div>
<div id="topvertbott">
  <p><code>border-color: red cyan gold;</code> is equivalent to</p>
  <ul>
    <li><code>border-top-color: red;</code></li>
    <li><code>border-right-color: cyan;</code></li>
    <li><code>border-bottom-color: gold;</code></li>
    <li><code>border-left-color: cyan;</code></li>
  </ul>
</div>
<div id="trbl">
  <p><code>border-color: red cyan black gold;</code> is equivalent to</p>
  <ul>
    <li><code>border-top-color: red;</code></li>
    <li><code>border-right-color: cyan;</code></li>
    <li><code>border-bottom-color: black;</code></li>
    <li><code>border-left-color: gold;</code></li>
  </ul>
</div>
```

#### CSS

[css]

```css
#justone {
  border-color: red;
}

#horzvert {
  border-color: gold red;
}

#topvertbott {
  border-color: red cyan gold;
}

#trbl {
  border-color: red cyan black gold;
}

/* Set width and style for all divs */
div {
  border: solid 0.3em;
  width: auto;
  margin: 0.5em;
  padding: 0.5em;
}

ul {
  margin: 0;
  list-style: none;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  logical-shorthand-keyword]](https://drafts.csswg.org/css-logical/#logical-shorthand-keyword)

[CSS Backgrounds and Borders Module Level 3\
  [\# border-color]](https://drafts.csswg.org/css-backgrounds/#border-color)
  ------------------------------------------------------------------------------------------------------

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

`border-color`

1

12

1Firefox also supports the following non-standard CSS properties to set
the border sides to multiple colors:
[`-moz-border-top-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-top-colors),
[`-moz-border-right-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-right-colors),
[`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors),
[`-moz-border-left-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-left-colors)

4

3.5

1

4

18

4Firefox also supports the following non-standard CSS properties to set
the border sides to multiple colors:
[`-moz-border-top-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-top-colors),
[`-moz-border-right-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-right-colors),
[`-moz-border-bottom-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-bottom-colors),
[`-moz-border-left-colors`](https://developer.mozilla.org/docs/Web/CSS/-moz-border-left-colors)

10.1

1

1.0

See also
--------

- Border-color related CSS properties: [`border`](border.md),
    [`border-top-color`](border-top-color.md),
    [`border-right-color`](border-right-color.md),
    [`border-bottom-color`](border-bottom-color.md),
    [`border-left-color`](border-left-color.md),
- Other border-related CSS properties: [`border-width`](border-width.md),
    [`border-style`](border-style.md)
- The [`<color>`](color_value.md) data type
- Other color-related properties: [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), [`caret-color`](caret-color.md), and
    [`column-rule-color`](column-rule-color.md)
- [](applying_color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-color>

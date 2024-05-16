column-rule-color
=================

The `column-rule-color`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the color of the line drawn between columns in a multi-column layout.

Try it
------

Syntax
------

[css]

```css
/* <color> values */
column-rule-color: red;
column-rule-color: rgb(192 56 78);
column-rule-color: transparent;
column-rule-color: hsl(0 100% 50% / 0.6);

/* Global values */
column-rule-color: inherit;
column-rule-color: initial;
column-rule-color: revert;
column-rule-color: revert-layer;
column-rule-color: unset;
```

The `column-rule-color` property is specified as a single `<color>`
value.

### Values

[`<color>`](color_value.md)

:   The color of the rule that separates columns.

Formal definition
-----------------

  ---------------------------------- --------------------------------------
  [Initial value](initial_value.md)     `currentcolor`
  Applies to                         multicol elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   computed color
  Animation type                     a [color](color_value.md#interpolation)
  ---------------------------------- --------------------------------------

Formal syntax
-------------

```
column-rule-color = 
  <color>  
```

Examples
--------

### Setting a blue column rule

#### HTML

[html]

```html
<p>
  This is a bunch of text split into three columns. The `column-rule-color`
  property is used to change the color of the line that is drawn between
  columns. Don't you think that's wonderful?
</p>
```

#### CSS

[css]

```css
p {
  column-count: 3;
  column-rule-style: solid;
  column-rule-color: blue;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  [\# crc]](https://drafts.csswg.org/css-multicol/#crc)

  -----------------------------------------------------------------------

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

`column-rule-color`

501

1212

523.5--74

10

1511.1

93

50≤37

5018

524

1411.1

91

5.01.0

See also
--------

- The [`<color>`](color_value.md) data type
- Other color-related properties: [`color`](_Resources/Markup%20And%20Styling/css/color.md),
    [`background-color`](background-color.md),
    [`border-color`](border-color.md), [`outline-color`](outline-color.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-emphasis-color`](text-emphasis-color.md),
    [`text-shadow`](text-shadow.md), and [`caret-color`](caret-color.md)
- [](applying_color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-color>

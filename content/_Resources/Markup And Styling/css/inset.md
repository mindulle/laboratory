inset
=====

The `inset` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property is a shorthand that corresponds to the [`top`](top.md),
[`right`](right.md), [`bottom`](bottom.md), and/or [`left`](left.md) properties.
It has the same multi-value syntax of the [`margin`](margin.md) shorthand.

Try it
------

While part of the *CSS Logical Properties* specification, it does not
define *logical* offsets. It defines *physical* offsets, regardless of
the element\'s writing mode, directionality, and text orientation.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`top`](top.md)
- [`right`](right.md)
- [`bottom`](bottom.md)
- [`left`](left.md)

Syntax
------

[css]

```css
/* <length> values */
inset: 10px; /* value applied to all edges */
inset: 4px 8px; /* top/bottom left/right */
inset: 5px 15px 10px; /* top left/right bottom */
inset: 2.4em 3em 3em 3em; /* top right bottom left */

/* <percentage>s of the width (left/right) or height (top/bottom) of the containing block */
inset: 10% 5% 5% 5%;

/* Keyword value */
inset: auto;

/* Global values */
inset: inherit;
inset: initial;
inset: revert;
inset: revert-layer;
inset: unset;
```

### Values

The `inset` property takes the same values as the [`left`](left.md)
property.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`top`](top.md): `auto`          |
|                                   | -   [`bottom`](bottom.md): `auto`    |
|                                   | -   [`left`](left.md): `auto`        |
|                                   | -   [`right`](right.md): `auto`      |
+-----------------------------------+-----------------------------------+
| Applies to                        | positioned elements               |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | relative to the containing        |
|                                   | block's size in the corresponding |
|                                   | axis (e.g. width for left or      |
|                                   | right, height for top or bottom)  |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`top`](top.md): if specified as |
|                                   |     a length, the corresponding   |
|                                   |     absolute length; if specified |
|                                   |     as a percentage, the          |
|                                   |     specified value; otherwise,   |
|                                   |     `auto`                        |
|                                   | -   [`bottom`](bottom.md): if        |
|                                   |     specified as a length, the    |
|                                   |     corresponding absolute        |
|                                   |     length; if specified as a     |
|                                   |     percentage, the specified     |
|                                   |     value; otherwise, `auto`      |
|                                   | -   [`left`](left.md): if specified  |
|                                   |     as a length, the              |
|                                   |     corresponding absolute        |
|                                   |     length; if specified as a     |
|                                   |     percentage, the specified     |
|                                   |     value; otherwise, `auto`      |
|                                   | -   [`right`](right.md): if          |
|                                   |     specified as a length, the    |
|                                   |     corresponding absolute        |
|                                   |     length; if specified as a     |
|                                   |     percentage, the specified     |
|                                   |     value; otherwise, `auto`      |
+-----------------------------------+-----------------------------------+
| Animation type                    | a [length](length.md#interpolation), |
|                                   | [](percentage.md#interpolation) |
|                                   | or calc();                        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
inset = 
  <top>  
```

Examples
--------

### Setting offsets for an element

#### HTML

[html]

```html
<div>
  <span class="exampleText">Example text</span>
</div>
```

#### CSS

[css]

```css
div {
  background-color: yellow;
  width: 150px;
  height: 120px;
  position: relative;
}

.exampleText {
  writing-mode: sideways-rl;
  position: absolute;
  inset: 20px 40px 30px 10px;
  background-color: #c8c800;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-inset]](https://drafts.csswg.org/css-logical/#propdef-inset)

  ------------------------------------------------------------------------------

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

`inset`

87

87

66

No

73

14.1

87

87

66

62

14.5

14.0

See also
--------

- The longhand box offset properties: [`top`](top.md), [`right`](right.md),
    [`bottom`](bottom.md), and [`left`](left.md).
- The mapped logical shorthands: [`inset-block`](inset-block.md) and
    [`inset-inline`](inset-inline.md)
- The [`margin`](margin.md) shorthand multi-value syntax.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/inset>

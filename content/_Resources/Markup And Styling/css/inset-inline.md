inset-inline
============

The `inset-inline`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical start and end offsets of an element in the inline direction,
which maps to physical offsets depending on the element\'s writing mode,
directionality, and text orientation. It corresponds to the [`top`](top.md)
and [`bottom`](bottom.md), or [`right`](right.md) and [`left`](left.md)
properties depending on the values defined for
[`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`inset-inline-end`](inset-inline-end.md)
- [`inset-inline-start`](inset-inline-start.md)

Syntax
------

[css]

```css
/* <length> values */
inset-inline: 3px 10px;
inset-inline: 2.4em 3em;
inset-inline: 10px; /* value applied to start and end */

/* <percentage>s of the width or height of the containing block */
inset-inline: 10% 5%;

/* Keyword value */
inset-inline: auto;

/* Global values */
inset-inline: inherit;
inset-inline: initial;
inset-inline: revert;
inset-inline: revert-layer;
inset-inline: unset;
```

### Values

The `inset-inline` property takes the same values as the [`left`](left.md)
property.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](inset-inline-start.md): |
|                                   |     `auto`                        |
|                                   | -   [](inset-inline-end.md): |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | positioned elements               |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | logical-width of containing block |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](inset-inline-start.md): |
|                                   |     same as box offsets:          |
|                                   |     [`top`](top.md),                 |
|                                   |     [`right`](right.md),             |
|                                   |     [`bottom`](bottom.md),           |
|                                   |     [`left`](left.md) properties     |
|                                   |     except that directions are    |
|                                   |     logical                       |
|                                   | -   [](inset-inline-end.md): |
|                                   |     same as box offsets:          |
|                                   |     [`top`](top.md),                 |
|                                   |     [`right`](right.md),             |
|                                   |     [`bottom`](bottom.md),           |
|                                   |     [`left`](left.md) properties     |
|                                   |     except that directions are    |
|                                   |     logical                       |
+-----------------------------------+-----------------------------------+
| Animation type                    | a [length](length.md#interpolation), |
|                                   | [](percentage.md#interpolation) |
|                                   | or calc();                        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
inset-inline = 
  <top>  
```

Examples
--------

### Setting inline start and end offsets

#### HTML

[html]

```html
<div>
  <p class="exampleText">Example text</p>
</div>
```

#### CSS

[css]

```css
div {
  background-color: yellow;
  width: 120px;
  height: 120px;
}

.exampleText {
  writing-mode: vertical-lr;
  position: relative;
  inset-inline: 20px 50px;
  background-color: #c8c800;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-inset-inline]](https://drafts.csswg.org/css-logical/#propdef-inset-inline)

  --------------------------------------------------------------------------------------------

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

`inset-inline`

87

87

6341--63

No

73

14.1

87

87

6341--63

62

14.5

14.0

See also
--------

- The mapped physical properties: [`top`](top.md), [`right`](right.md),
    [`bottom`](bottom.md), and [`left`](left.md)
- The mapped physical shortcut: [`inset`](_Resources/Markup%20And%20Styling/css/inset.md)
- The mapped block shortcut: [`inset-block`](inset-block.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/inset-inline>

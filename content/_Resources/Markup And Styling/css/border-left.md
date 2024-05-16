border-left
===========

The `border-left` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
all the properties of an element\'s left [border](border.md).

Try it
------

As with all shorthand properties, `border-left` always sets the values
of all of the properties that it can set, even if they are not
specified. It sets those that are not specified to their default values.
Consider the following code:

[css]

```css
border-left-style: dotted;
border-left: thick green;
```

It is actually the same as this one:

[css]

```css
border-left-style: dotted;
border-left: none thick green;
```

The value of [`border-left-style`](border-left-style.md) given before
`border-left` is ignored. Since the default value of
[`border-left-style`](border-left-style.md) is `none`, not specifying the
`border-style` part results in no border.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-left-color`](border-left-color.md)
- [`border-left-style`](border-left-style.md)
- [`border-left-width`](border-left-width.md)

Syntax
------

[css]

```css
border-left: 1px;
border-left: 2px dotted;
border-left: medium dashed blue;

/* Global values */
border-left: inherit;
border-left: initial;
border-left: revert;
border-left: revert-layer;
border-left: unset;
```

The three values of the shorthand property can be specified in any
order, and one or two of them may be omitted.

### Values

[`<br-width>`](#br-width)

:   See [`border-left-width`](border-left-width.md).

[`<br-style>`](#br-style)

:   See [`border-left-style`](border-left-style.md).

[`<color>`](color_value.md)

:   See [`border-left-color`](border-left-color.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-left-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-left-style.md): |
|                                   |     `none`                        |
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
|                                   | -   [](border-left-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-left-style.md) |
|                                   |     is `none` or `hidden`         |
|                                   | -   [](border-left-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-left-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-left-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](border-left-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-left-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-left = 
  <line-width>  ||
  <line-style>  ||
  <color>       

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           

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

### Applying a left border

#### HTML

[html]

```html
<div>This box has a border on the left side.</div>
```

#### CSS

[css]

```css
div {
  border-left: 4px dashed blue;
  background-color: gold;
  height: 100px;
  width: 100px;
  font-weight: bold;
  text-align: center;
}
```

#### Results

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  border-shorthands]](https://drafts.csswg.org/css-backgrounds/#border-shorthands)

  ------------------------------------------------------------------------------------------

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

`border-left`

1

12

1

4

3.5

1

4.4

18

4

14

1

1.0

See also
--------

- [`border`](border.md)
- [`border-block`](border-block.md)
- [`outline`](outline.md)
- [Backgrounds and borders](css_backgrounds_and_borders.md)
- [Learn CSS: Backgrounds and
    borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-left>

border-right
============

The `border-right` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
all the properties of an element\'s right [border](border.md).

Try it
------

As with all shorthand properties, `border-right` always sets the values
of all of the properties that it can set, even if they are not
specified. It sets those that are not specified to their default values.
Consider the following code:

[css]

```css
border-right-style: dotted;
border-right: thick green;
```

It is actually the same as this one:

[css]

```css
border-right-style: dotted;
border-right: none thick green;
```

The value of [`border-right-style`](border-right-style.md) given before
`border-right` is ignored. Since the default value of
[`border-right-style`](border-right-style.md) is `none`, not specifying the
`border-style` part results in no border.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-right-color`](border-right-color.md)
- [`border-right-style`](border-right-style.md)
- [`border-right-width`](border-right-width.md)

Syntax
------

[css]

```css
border-right: 1px;
border-right: 2px dotted;
border-right: medium dashed green;

/* Global values */
border-right: inherit;
border-right: initial;
border-right: revert;
border-right: revert-layer;
border-right: unset;
```

The three values of the shorthand property can be specified in any
order, and one or two of them may be omitted.

### Values

[`<br-width>`](#br-width)

:   See [`border-right-width`](border-right-width.md).

[`<br-style>`](#br-style)

:   See [`border-right-style`](border-right-style.md).

[`<color>`](color_value.md)

:   See [`border-right-color`](border-right-color.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-right-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-right-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-right-color.md): |
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
|                                   | -   [](border-right-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-right-style.md) |
|                                   |     is `none` or `hidden`         |
|                                   | -   [](border-right-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-right-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-right-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](border-right-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-right-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-right = 
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

### Applying a right border

#### HTML

[html]

```html
<div>This box has a border on the right side.</div>
```

#### CSS

[css]

```css
div {
  border-right: 4px dashed blue;
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

`border-right`

1

12

1

5.5

9.2

1

≤37

18

14

14

1

1.0

See also
--------

- [`border`](border.md)
- [`border-block`](border-block.md)
- [`outline`](outline.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-right>

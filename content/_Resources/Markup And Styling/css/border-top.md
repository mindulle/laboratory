border-top
==========

The `border-top` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
all the properties of an element\'s top [border](border.md).

Try it
------

As with all shorthand properties, `border-top` always sets the values of
all of the properties that it can set, even if they are not specified.
It sets those that are not specified to their default values. Consider
the following code:

[css]

```css
border-top-style: dotted;
border-top: thick green;
```

It is actually the same as this one:

[css]

```css
border-top-style: dotted;
border-top: none thick green;
```

The value of [`border-top-style`](border-top-style.md) given before
`border-top` is ignored. Since the default value of
[`border-top-style`](border-top-style.md) is `none`, not specifying the
`border-style` part results in no border.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-top-color`](border-top-color.md)
- [`border-top-style`](border-top-style.md)
- [`border-top-width`](border-top-width.md)

Syntax
------

[css]

```css
border-top: 1px;
border-top: 2px dotted;
border-top: medium dashed green;

/* Global values */
border-top: inherit;
border-top: initial;
border-top: revert;
border-top: revert-layer;
border-top: unset;
```

The three values of the shorthand property can be specified in any
order, and one or two of them may be omitted.

### Values

[`<br-width>`](#br-width)

:   See [`border-top-width`](border-top-width.md).

[`<br-style>`](#br-style)

:   See [`border-top-style`](border-top-style.md).

[`<color>`](color_value.md)

:   See [`border-top-color`](border-top-color.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-top-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-top-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-top-color.md): |
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
|                                   | -   [](border-top-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-top-style.md) |
|                                   |     is `none` or `hidden`         |
|                                   | -   [](border-top-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-top-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-top-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](border-top-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-top-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-top = 
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

### Applying a top border

#### HTML

[html]

```html
<div>This box has a border on the top side.</div>
```

#### CSS

[css]

```css
div {
  border-top: 4px dashed blue;
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

`border-top`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-top>

border-bottom
=============

The `border-bottom` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets an
element\'s bottom [border](border.md). It sets the values of
[`border-bottom-width`](border-bottom-width.md),
[`border-bottom-style`](border-bottom-style.md) and
[`border-bottom-color`](border-bottom-color.md).

Try it
------

As with all shorthand properties, `border-bottom` always sets the values
of all of the properties that it can set, even if they are not
specified. It sets those that are not specified to their default values.
Consider the following code:

[css]

```css
border-bottom-style: dotted;
border-bottom: thick green;
```

It is actually the same as this one:

[css]

```css
border-bottom-style: dotted;
border-bottom: none thick green;
```

The value of [`border-bottom-style`](border-bottom-style.md) given before
`border-bottom` is ignored. Since the default value of
[`border-bottom-style`](border-bottom-style.md) is `none`, not specifying
the `border-style` part results in no border.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-bottom-color`](border-bottom-color.md)
- [`border-bottom-style`](border-bottom-style.md)
- [`border-bottom-width`](border-bottom-width.md)

Syntax
------

[css]

```css
border-bottom: 1px;
border-bottom: 2px dotted;
border-bottom: medium dashed blue;

/* Global values */
border-bottom: inherit;
border-bottom: initial;
border-bottom: revert;
border-bottom: revert-layer;
border-bottom: unset;
```

The three values of the shorthand property can be specified in any
order, and one or two of them may be omitted.

### Values

[`<br-width>`](#br-width)

:   See [`border-bottom-width`](border-bottom-width.md).

[`<br-style>`](#br-style)

:   See [`border-bottom-style`](border-bottom-style.md).

[`<color>`](color_value.md)

:   See [`border-bottom-color`](border-bottom-color.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-bottom-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-bottom-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-bottom-color.md): |
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
|                                   | -   [](border-bottom-width.md): |
|                                   |     the absolute length or `0` if |
|                                   |     [](border-bottom-style.md) |
|                                   |     is `none` or `hidden`         |
|                                   | -   [](border-bottom-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-bottom-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-bottom-color.md): |
|                                   |     a                             |
|                                   |     [](color_value.md#interpolation) |
|                                   | -   [](border-bottom-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-bottom-width.md): |
|                                   |     a                             |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-bottom = 
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

### Applying a bottom border

#### HTML

[html]

```html
<div>This box has a border on the bottom side.</div>
```

#### CSS

[css]

```css
div {
  border-bottom: 4px dashed blue;
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

`border-bottom`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/border-bottom>

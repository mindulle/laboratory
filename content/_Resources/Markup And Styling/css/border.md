border
======

The `border` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets an
element\'s border. It sets the values of [`border-width`](border-width.md),
[`border-style`](border-style.md), and [`border-color`](border-color.md).

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-color`](border-color.md)
- [`border-style`](border-style.md)
- [`border-width`](border-width.md)

Syntax
------

[css]

```css
/* style */
border: solid;

/* width | style */
border: 2px dotted;

/* style | color */
border: outset #f33;

/* width | style | color */
border: medium dashed green;

/* Global values */
border: inherit;
border: initial;
border: revert;
border: revert-layer;
border: unset;
```

The `border` property may be specified using one, two, or three of the
values listed below. The order of the values does not matter.

**Note:** The border will be invisible if its style is not defined. This
is because the style defaults to `none`.

### Values

[`<line-width>`](#line-width)

:   Sets the thickness of the border. Defaults to `medium` if absent.
    See [`border-width`](border-width.md).

[`<line-style>`](line-style.md)

:   Sets the style of the border. Defaults to `none` if absent. See
    [`border-style`](border-style.md).

[`<color>`](color_value.md)

:   Sets the color of the border. Defaults to `currentcolor` if absent.
    See [`border-color`](border-color.md).

Description
-----------

As with all shorthand properties, any omitted sub-values will be set to
their [initial value](initial_value.md). Importantly, `border` cannot be
used to specify a custom value for [`border-image`](border-image.md), but
instead sets it to its initial value, i.e., `none`.

The `border` shorthand is especially useful when you want all four
borders to be the same. To make them different from each other, however,
you can use the longhand [`border-width`](border-width.md),
[`border-style`](border-style.md), and [`border-color`](border-color.md)
properties, which accept different values for each side. Alternatively,
you can target one border at a time with the physical (e.g.,
[`border-top`](border-top.md) ) and logical (e.g.,
[`border-block-start`](border-block-start.md)) border properties.

### Borders vs. outlines

Borders and [outlines](outline.md) are very similar. However, outlines
differ from borders in the following ways:

- Outlines never take up space, as they are drawn outside of an
    element\'s content.
- According to the spec, outlines don\'t have to be rectangular,
    although they usually are.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   |   [`border-width`](border-width.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-top-width.md): |
|                                   |         `medium`                  |
|                                   |     -   [](border-right-width.md): |
|                                   |         `medium`                  |
|                                   |     -   [](border-bottom-width.md): |
|                                   |         `medium`                  |
|                                   |     -   [](border-left-width.md): |
|                                   |         `medium`                  |
|                                   | -                                 |
|                                   |   [`border-style`](border-style.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-top-style.md): |
|                                   |         `none`                    |
|                                   |     -   [](border-right-style.md): |
|                                   |         `none`                    |
|                                   |     -   [](border-bottom-style.md): |
|                                   |         `none`                    |
|                                   |     -   [](border-left-style.md): |
|                                   |         `none`                    |
|                                   | -                                 |
|                                   |   [`border-color`](border-color.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-top-color.md): |
|                                   |         `currentcolor`            |
|                                   |     -   [](border-right-color.md): |
|                                   |         `currentcolor`            |
|                                   |     -   [](border-bottom-color.md): |
|                                   |         `currentcolor`            |
|                                   |     -   [](border-left-color.md): |
|                                   |         `currentcolor`            |
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
|                                   | -                                 |
|                                   |   [`border-width`](border-width.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-bottom-width.md): |
|                                   |         the absolute length or    |
|                                   |         `0` if                    |
|                                   |         [](border-bottom-style.md) |
|                                   |         is `none` or `hidden`     |
|                                   |     -   [](border-left-width.md): |
|                                   |         the absolute length or    |
|                                   |         `0` if                    |
|                                   |         [](border-left-style.md) |
|                                   |         is `none` or `hidden`     |
|                                   |     -   [](border-right-width.md): |
|                                   |         the absolute length or    |
|                                   |         `0` if                    |
|                                   |         [](border-right-style.md) |
|                                   |         is `none` or `hidden`     |
|                                   |     -   [](border-top-width.md): |
|                                   |         the absolute length or    |
|                                   |         `0` if                    |
|                                   |         [](border-top-style.md) |
|                                   |         is `none` or `hidden`     |
|                                   | -                                 |
|                                   |   [`border-style`](border-style.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-bottom-style.md): |
|                                   |         as specified              |
|                                   |     -   [](border-left-style.md): |
|                                   |         as specified              |
|                                   |     -   [](border-right-style.md): |
|                                   |         as specified              |
|                                   |     -   [](border-top-style.md): |
|                                   |         as specified              |
|                                   | -                                 |
|                                   |   [`border-color`](border-color.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-bottom-color.md): |
|                                   |         computed color            |
|                                   |     -   [](border-left-color.md): |
|                                   |         computed color            |
|                                   |     -   [](border-right-color.md): |
|                                   |         computed color            |
|                                   |     -   [](border-top-color.md): |
|                                   |         computed color            |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   |   [`border-color`](border-color.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-bottom-color.md): |
|                                   |         a                         |
|                                   |         [](color_value.md#interpolation) |
|                                   |     -   [](border-left-color.md): |
|                                   |         a                         |
|                                   |         [](color_value.md#interpolation) |
|                                   |     -   [](border-right-color.md): |
|                                   |         a                         |
|                                   |         [](color_value.md#interpolation) |
|                                   |     -   [](border-top-color.md): |
|                                   |         a                         |
|                                   |         [](color_value.md#interpolation) |
|                                   | -                                 |
|                                   |   [`border-style`](border-style.md): |
|                                   |     discrete                      |
|                                   | -                                 |
|                                   |   [`border-width`](border-width.md): |
|                                   |     as each of the properties of  |
|                                   |     the shorthand:\               |
|                                   |     -   [](border-bottom-width.md): |
|                                   |         a                         |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
|                                   |     -   [](border-left-width.md): |
|                                   |         a                         |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
|                                   |     -   [](border-right-width.md): |
|                                   |         a                         |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
|                                   |     -   [](border-top-width.md): |
|                                   |         a                         |
|                                   |                                   |
|                                   |    [length](length.md#interpolation) |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border = 
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

### Setting a pink outset border

#### HTML

[html]

```html
<div>I have a border, an outline, and a box shadow! Amazing, isn't it?</div>
```

#### CSS

[css]

```css
div {
  border: 0.5rem outset pink;
  outline: 0.5rem solid khaki;
  box-shadow: 0 0 0 2rem skyblue;
  border-radius: 12px;
  font: bold 1rem sans-serif;
  margin: 2rem;
  padding: 1rem;
  outline-offset: 0.5rem;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  propdef-border]](https://drafts.csswg.org/css-backgrounds/#propdef-border)

  ------------------------------------------------------------------------------------

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

`border`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

See also
--------

- [`border-width`](border-width.md)
- [`border-style`](border-style.md)
- [`border-color`](border-color.md)
- [`outline`](outline.md)
- [Backgrounds and borders](css_backgrounds_and_borders.md)
- [Learn CSS: Backgrounds and
    borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border>

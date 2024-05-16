border-block-end
================

The `border-block-end`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a
[shorthand property](shorthand_properties.md) for setting the individual
logical block-end border property values in a single place in the style
sheet.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-block-end-color`](border-block-end-color.md)
- [`border-block-end-style`](border-block-end-style.md)
- [`border-block-end-width`](border-block-end-width.md)

Syntax
------

[css]

```css
border-block-end: 1px;
border-block-end: 2px dotted;
border-block-end: medium dashed blue;

/* Global values */
border-block-end: inherit;
border-block-end: initial;
border-block-end: revert;
border-block-end: revert-layer;
border-block-end: unset;
```

`border-block-end` can be used to set the values for one or more of
[`border-block-end-width`](border-block-end-width.md),
[`border-block-end-style`](border-block-end-style.md), and
[`border-block-end-color`](border-block-end-color.md). The physical border
to which it maps depends on the element\'s writing mode, directionality,
and text orientation. It corresponds to the [`border-top`](border-top.md),
[`border-right`](border-right.md), [`border-bottom`](border-bottom.md), or
[`border-left`](border-left.md) property depending on the values defined
for [`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

Related properties are [`border-block-start`](border-block-start.md),
[`border-inline-start`](border-inline-start.md), and
[`border-inline-end`](border-inline-end.md), which define the other borders
of the element.

### Values

The `border-block-end` is specified with one or more of the following,
in any order:

[`<'border-width'>`](#border-width)

:   The width of the border. See [`border-width`](border-width.md).

[`<'border-style'>`](#border-style)

:   The line style of the border. See [`border-style`](border-style.md).

[`<color>`](color_value.md)

:   The color of the border.

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
| Applies to                        | all elements                      |
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
|                                   | -   [](border-block-end-color.md): |
|                                   |     by computed value type        |
|                                   | -   [](border-block-end-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-block-end-width.md): |
|                                   |     by computed value type        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-block-end = 
  <'border-top-width'>  ||
  <'border-top-style'>  ||
  <color>               
```

Examples
--------

### Border with vertical text

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
  writing-mode: vertical-rl;
  border-block-end: 5px dashed blue;
}
```

#### Results

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  border-shorthands]](https://drafts.csswg.org/css-logical/#border-shorthands)

  --------------------------------------------------------------------------------------

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

`border-block-end`

69

79

41

No

56

12.1

69

69

41

48

12.2

10.0

See also
--------

- [](css_logical_properties_and_values.md)
- This property maps to one of the physical border properties:
    [`border-top`](border-top.md), [`border-right`](border-right.md),
    [`border-bottom`](border-bottom.md), or [`border-left`](border-left.md).
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end>

border-block-start
==================

The `border-block-start`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a
[shorthand property](shorthand_properties.md) for setting the individual
logical block-start border property values in a single place in the
style sheet.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-block-start-color`](border-block-start-color.md)
- [`border-block-start-style`](border-block-start-style.md)
- [`border-block-start-width`](border-block-start-width.md)

Syntax
------

[css]

```css
border-block-start: 1px;
border-block-start: 2px dotted;
border-block-start: medium dashed blue;

/* Global values */
border-block-start: inherit;
border-block-start: initial;
border-block-start: revert;
border-block-start: revert-layer;
border-block-start: unset;
```

`border-block-start` can be used to set the values for one or more of
[`border-block-start-width`](border-block-start-width.md),
[`border-block-start-style`](border-block-start-style.md), and
[`border-block-start-color`](border-block-start-color.md). The physical
border to which it maps depends on the element\'s writing mode,
directionality, and text orientation. It corresponds to the
[`border-top`](border-top.md), [`border-right`](border-right.md),
[`border-bottom`](border-bottom.md), or [`border-left`](border-left.md)
property depending on the values defined for
[`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

Related properties are [`border-block-end`](border-block-end.md),
[`border-inline-start`](border-inline-start.md), and
[`border-inline-end`](border-inline-end.md), which define the other borders
of the element.

### Values

The `border-block-start` is specified with one or more of the following,
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
|                                   | -   [`color`](_Resources/Markup%20And%20Styling/css/color.md):             |
|                                   |     `canvastext`                  |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
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
|                                   | -   [](border-block-start-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-block-start-color.md): |
|                                   |     by computed value type        |
|                                   | -   [](border-block-start-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-block-start-width.md): |
|                                   |     by computed value type        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-block-start = 
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
  border-block-start: 5px dashed blue;
}
```

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

`border-block-start`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-start>

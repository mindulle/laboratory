border-inline
=============

The `border-inline`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a
[shorthand property](shorthand_properties.md) for setting the individual
logical inline border property values in a single place in the style
sheet.

Try it
------

The physical borders to which `border-inline` maps depends on the
element\'s writing mode, directionality, and text orientation. It
corresponds to the [`border-top`](border-top.md) and
[`border-bottom`](border-bottom.md) or [`border-right`](border-right.md), and
[`border-left`](border-left.md) properties, depending on the values defined
for [`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

The borders in the other dimension can be set with
[`border-block`](border-block.md), which sets
[`border-block-start`](border-block-start.md), and
[`border-block-end`](border-block-end.md).

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-inline-color`](border-inline-color.md)
- [`border-inline-style`](border-inline-style.md)
- [`border-inline-width`](border-inline-width.md)

Syntax
------

[css]

```css
border-inline: 1px;
border-inline: 2px dotted;
border-inline: medium dashed blue;

/* Global values */
border-inline: inherit;
border-inline: initial;
border-inline: revert;
border-inline: revert-layer;
border-inline: unset;
```

### Values

The `border-inline` is specified with one or more of the following, in
any order:

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
|                                   | -   [](border-inline-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-inline-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-inline-color.md): |
|                                   |     `currentcolor`                |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-inline-width.md): |
|                                   |     absolute length; `0` if the   |
|                                   |     border style is `none` or     |
|                                   |     `hidden`                      |
|                                   | -   [](border-inline-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-inline-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-inline-color.md): |
|                                   |     by computed value type        |
|                                   | -   [](border-inline-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-inline-width.md): |
|                                   |     by computed value type        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-inline = 
  <'border-block-start'>  
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
  border-inline: 5px dashed blue;
}
```

#### Results

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-border-inline]](https://drafts.csswg.org/css-logical/#propdef-border-inline)

  ----------------------------------------------------------------------------------------------

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

`border-inline`

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

- [](css_logical_properties_and_values.md)
- This property maps to one of the physical border properties:
    [`border-top`](border-top.md), [`border-right`](border-right.md),
    [`border-bottom`](border-bottom.md), or [`border-left`](border-left.md).
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline>

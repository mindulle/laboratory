border-block
============

The `border-block`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a
[shorthand property](shorthand_properties.md) for setting the individual
logical block border property values in a single place in the style
sheet.

Try it
------

`border-block` can be used to set the values for one or more of
[`border-block-width`](border-block-width.md),
[`border-block-style`](border-block-style.md), and
[`border-block-color`](border-block-color.md) setting both the start and
end in the block dimension at once. The physical borders to which it
maps depends on the element\'s writing mode, directionality, and text
orientation. It corresponds to the [`border-top`](border-top.md) and
[`border-bottom`](border-bottom.md) or [`border-right`](border-right.md), and
[`border-left`](border-left.md) properties depending on the values defined
for [`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

The borders in the other dimension can be set with
[`border-inline`](border-inline.md), which sets
[`border-inline-start`](border-inline-start.md), and
[`border-inline-end`](border-inline-end.md).

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`border-block-color`](border-block-color.md)
- [`border-block-style`](border-block-style.md)
- [`border-block-width`](border-block-width.md)

Syntax
------

[css]

```css
border-block: 1px;
border-block: 2px dotted;
border-block: medium dashed blue;

/* Global values */
border-block: inherit;
border-block: initial;
border-block: revert;
border-block: revert-layer;
border-block: unset;
```

### Values

The `border-block` is specified with one or more of the following, in
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
|                                   | -   [](border-block-width.md): |
|                                   |     `medium`                      |
|                                   | -   [](border-block-style.md): |
|                                   |     `none`                        |
|                                   | -   [](border-block-color.md): |
|                                   |     `currentcolor`                |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-block-width.md): |
|                                   |     absolute length; `0` if the   |
|                                   |     border style is `none` or     |
|                                   |     `hidden`                      |
|                                   | -   [](border-block-style.md): |
|                                   |     as specified                  |
|                                   | -   [](border-block-color.md): |
|                                   |     computed color                |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](border-block-width.md): |
|                                   |     by computed value type        |
|                                   | -   [](border-block-style.md): |
|                                   |     discrete                      |
|                                   | -   [](border-block-color.md): |
|                                   |     by computed value type        |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
border-block = 
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
  border-block: 5px dashed blue;
}
```

#### Results

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-border-block]](https://drafts.csswg.org/css-logical/#propdef-border-block)

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

`border-block`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/border-block>

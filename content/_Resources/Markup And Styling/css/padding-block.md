padding-block
=============

The `padding-block`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](shorthand_properties.md) defines the logical block start and end
padding of an element, which maps to physical padding properties
depending on the element\'s writing mode, directionality, and text
orientation.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`padding-block-end`](padding-block-end.md)
- [`padding-block-start`](padding-block-start.md)

Syntax
------

[css]

```css
/* <length> values */
padding-block: 10px 20px; /* An absolute length */
padding-block: 1em 2em; /* relative to the text size */
padding-block: 10px; /* sets both start and end values */

/* <percentage> values */
padding-block: 5% 2%; /* relative to the nearest block container's width */

/* Global values */
padding-block: inherit;
padding-block: initial;
padding-block: revert;
padding-block: revert-layer;
padding-block: unset;
```

The `padding-block` property may be specified with one or two values. If
one value is given, it is used as the value for both
[`padding-block-start`](padding-block-start.md) and
[`padding-block-end`](padding-block-end.md). If two values are given, the
first is used for [`padding-block-start`](padding-block-start.md) and the
second for [`padding-block-end`](padding-block-end.md).

### Values

The `padding-block` property takes the same values as the
[`padding-left`](padding-left.md) property.

Description
-----------

These values corresponds to the [`padding-top`](padding-top.md) and
[`padding-bottom`](padding-bottom.md), or [`padding-right`](padding-right.md),
and [`padding-left`](padding-left.md) property depending on the values
defined for [`writing-mode`](writing-mode.md), [`direction`](direction.md),
and [`text-orientation`](text-orientation.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](padding-block-start.md): |
|                                   |     `0`                           |
|                                   | -   [](padding-block-end.md): |
|                                   |     `0`                           |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements, except              |
|                                   | `table-row-group`,                |
|                                   | `table-header-group`,             |
|                                   | `table-footer-group`,             |
|                                   | `table-row`, `table-column-group` |
|                                   | and `table-column`                |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | logical-width of containing block |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](padding-block-start.md): |
|                                   |     as [`<length>`](length.md)       |
|                                   | -   [](padding-block-end.md): |
|                                   |     as [`<length>`](length.md)       |
+-----------------------------------+-----------------------------------+
| Animation type                    | a [length](length.md#interpolation)  |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
padding-block = 
  <'padding-top'>  
```

Examples
--------

### Setting block padding for vertical text

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
  padding-block: 20px 40px;
  background-color: #c8c800;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-padding-block]](https://drafts.csswg.org/css-logical/#propdef-padding-block)

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

`padding-block`

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
- The mapped physical properties: [`padding-top`](padding-top.md),
    [`padding-right`](padding-right.md),
    [`padding-bottom`](padding-bottom.md), and
    [`padding-left`](padding-left.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/padding-block>

padding-inline
==============

The `padding-inline`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](shorthand_properties.md) defines the logical inline start and end
padding of an element, which maps to physical padding properties
depending on the element\'s writing mode, directionality, and text
orientation.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`padding-inline-end`](padding-inline-end.md)
- [`padding-inline-start`](padding-inline-start.md)

Syntax
------

[css]

```css
/* <length> values */
padding-inline: 10px 20px; /* An absolute length */
padding-inline: 1em 2em; /* relative to the text size */
padding-inline: 10px; /* sets both start and end values */

/* <percentage> values */
padding-inline: 5% 2%; /* relative to the nearest block container's width */

/* Global values */
padding-inline: inherit;
padding-inline: initial;
padding-inline: revert;
padding-inline: revert-layer;
padding-inline: unset;
```

The `padding-inline` property may be specified with one or two values.
If one value is given, it is used as the value for both
[`padding-inline-start`](padding-inline-start.md) and
[`padding-inline-end`](padding-inline-end.md). If two values are given, the
first is used for [`padding-inline-start`](padding-inline-start.md) and the
second for [`padding-inline-end`](padding-inline-end.md).

### Values

[`<length>`](length.md)

:   The size of the padding as a fixed value. Must be nonnegative.

[`<percentage>`](percentage.md)

:   The size of the padding as a percentage, relative to the inline size
    (*width* in a horizontal language, defined by
    [`writing-mode`](writing-mode.md)) of the [](containing_block.md). Must be nonnegative.

Description
-----------

Values for this property correspond to the [`padding-top`](padding-top.md)
and [`padding-bottom`](padding-bottom.md), or
[`padding-right`](padding-right.md), and [`padding-left`](padding-left.md)
property depending on the values defined for
[`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](padding-inline-start.md): |
|                                   |     `0`                           |
|                                   | -   [](padding-inline-end.md): |
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
|                                   | -   [](padding-inline-start.md): |
|                                   |     as [`<length>`](length.md)       |
|                                   | -   [](padding-inline-end.md): |
|                                   |     as [`<length>`](length.md)       |
+-----------------------------------+-----------------------------------+
| Animation type                    | a [length](length.md#interpolation)  |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
padding-inline = 
  <'padding-top'>  
```

Examples
--------

### Setting inline padding for vertical text

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
  padding-inline: 20px 40px;
  background-color: #c8c800;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-padding-inline]](https://drafts.csswg.org/css-logical/#propdef-padding-inline)

  ------------------------------------------------------------------------------------------------

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

`padding-inline`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/padding-inline>

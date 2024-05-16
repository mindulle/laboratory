margin-inline
=============

The `margin-inline`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](shorthand_properties.md) is a shorthand property that defines
both the logical inline start and end margins of an element, which maps
to physical margins depending on the element\'s writing mode,
directionality, and text orientation.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`margin-inline-start`](margin-inline-start.md)
- [`margin-inline-end`](margin-inline-end.md)

Syntax
------

[css]

```css
/* <length> values */
margin-inline: 10px 20px; /* An absolute length */
margin-inline: 1em 2em; /* relative to the text size */
margin-inline: 5% 2%; /* relative to the nearest block container's width */
margin-inline: 10px; /* sets both start and end values */

/* Keyword values */
margin-inline: auto;

/* Global values */
margin-inline: inherit;
margin-inline: initial;
margin-inline: revert;
margin-inline: revert-layer;
margin-inline: unset;
```

This property corresponds to the [`margin-top`](margin-top.md) and
[`margin-bottom`](margin-bottom.md), or the [`margin-right`](margin-right.md)
and [`margin-left`](margin-left.md) properties, depending on the values
defined for [`writing-mode`](writing-mode.md), [`direction`](direction.md),
and [`text-orientation`](text-orientation.md).

The `margin-inline` property may be specified using one or two values.

- When **one** value is specified, it applies the same margin to
    **both start and end**.
- When **two** values are specified, the first margin applies to the
    **start**, the second to the **end**.

### Values

The `margin-inline` property takes the same values as the
[`margin`](margin.md#values) property.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](margin-inline-start.md): |
|                                   |     `0`                           |
|                                   | -   [](margin-inline-end.md): |
|                                   |     `0`                           |
+-----------------------------------+-----------------------------------+
| Applies to                        | same as [`margin`](margin.md)        |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | depends on layout model           |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](margin-inline-start.md): |
|                                   |     if specified as a length, the |
|                                   |     corresponding absolute        |
|                                   |     length; if specified as a     |
|                                   |     percentage, the specified     |
|                                   |     value; otherwise, `auto`      |
|                                   | -   [](margin-inline-end.md): |
|                                   |     if specified as a length, the |
|                                   |     corresponding absolute        |
|                                   |     length; if specified as a     |
|                                   |     percentage, the specified     |
|                                   |     value; otherwise, `auto`      |
+-----------------------------------+-----------------------------------+
| Animation type                    | a [length](length.md#interpolation)  |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
margin-inline = 
  <'margin-top'>  
```

Examples
--------

### Setting inline start and end margins

#### CSS

[css]

```css
div {
  background-color: yellow;
  width: 120px;
  height: auto;
  border: 1px solid green;
}

p {
  margin: 0;
  margin-inline: 20px 40px;
  background-color: tan;
}

.verticalExample {
  writing-mode: vertical-rl;
}
```

#### HTML

[html]

```html
<div>
  <p>Example text</p>
</div>
<div class="verticalExample">
  <p>Example text</p>
</div>
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-margin-inline]](https://drafts.csswg.org/css-logical/#propdef-margin-inline)

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

`margin-inline`

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
- The mapped physical properties: [`margin-top`](margin-top.md),
    [`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md),
    and [`margin-left`](margin-left.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline>

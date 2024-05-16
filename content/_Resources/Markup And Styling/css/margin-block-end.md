margin-block-end
================

The `margin-block-end`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical block end margin of an element, which maps to a physical
margin depending on the element\'s writing mode, directionality, and
text orientation.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
margin-block-end: 10px; /* An absolute length */
margin-block-end: 1em; /* relative to the text size */
margin-block-end: 5%; /* relative to the nearest block container's width */

/* Keyword values */
margin-block-end: auto;

/* Global values */
margin-block-end: inherit;
margin-block-end: initial;
margin-block-end: revert;
margin-block-end: revert-layer;
margin-block-end: unset;
```

It corresponds to the [`margin-top`](margin-top.md),
[`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md), or
[`margin-left`](margin-left.md) property depending on the values defined
for [`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

It relates to [`margin-block-start`](margin-block-start.md),
[`margin-inline-start`](margin-inline-start.md), and
[`margin-inline-end`](margin-inline-end.md), which define the other margins
of the element.

### Values

The `margin-block-end` property takes the same values as the
[`margin-left`](margin-left.md) property.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         same as [`margin`](margin.md)
  [Inherited](inheritance.md)           no
  Percentages                        depends on layout model
  [Computed value](computed_value.md)   if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, `auto`
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
margin-block-end = 
  <'margin-top'>  
```

Examples
--------

### Setting block end margin

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
  margin-block-end: 20px;
  background-color: #c8c800;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  margin-properties]](https://drafts.csswg.org/css-logical/#margin-properties)

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

`margin-block-end`

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
- The mapped physical properties: [`margin-top`](margin-top.md),
    [`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md),
    and [`margin-left`](margin-left.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block-end>

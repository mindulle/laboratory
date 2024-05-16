margin-block-start
==================

The `margin-block-start`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical block start margin of an element, which maps to a physical
margin depending on the element\'s writing mode, directionality, and
text orientation.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
margin-block-start: 10px; /* An absolute length */
margin-block-start: 1em; /* relative to the text size */
margin-block-start: 5%; /* relative to the nearest block container's width */

/* Keyword values */
margin-block-start: auto;

/* Global values */
margin-block-start: inherit;
margin-block-start: initial;
margin-block-start: revert;
margin-block-start: revert-layer;
margin-block-start: unset;
```

It corresponds to the [`margin-top`](margin-top.md),
[`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md), or
[`margin-left`](margin-left.md) property depending on the values defined
for [`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

It relates to [`margin-block-end`](margin-block-end.md),
[`margin-inline-start`](margin-inline-start.md), and
[`margin-inline-end`](margin-inline-end.md), which define the other margins
of the element.

### Values

The `margin-block-start` property takes the same values as the
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
margin-block-start = 
  <'margin-top'>  
```

Examples
--------

### Setting block start margin

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
  writing-mode: vertical-lr;
  margin-block-start: 20px;
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

`margin-block-start`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-block-start>

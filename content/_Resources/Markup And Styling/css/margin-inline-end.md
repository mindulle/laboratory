margin-inline-end
=================

The `margin-inline-end`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical inline end margin of an element, which maps to a physical
margin depending on the element\'s writing mode, directionality, and
text orientation. In other words, it corresponds to the
[`margin-top`](margin-top.md), [`margin-right`](margin-right.md),
[`margin-bottom`](margin-bottom.md) or [`margin-left`](margin-left.md)
property depending on the values defined for
[`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

Try it
------

Syntax
------

[css]

```css
/* <length> values */
margin-inline-end: 10px; /* An absolute length */
margin-inline-end: 1em; /* relative to the text size */
margin-inline-end: 5%; /* relative to the nearest block container's width */

/* Keyword values */
margin-inline-end: auto;

/* Global values */
margin-inline-end: inherit;
margin-inline-end: initial;
margin-inline-end: revert;
margin-inline-end: revert-layer;
margin-inline-end: unset;
```

It relates to [`margin-block-start`](margin-block-start.md),
[`margin-block-end`](margin-block-end.md), and
[`margin-inline-start`](margin-inline-start.md), which define the other
margins of the element.

### Values

The `margin-inline-end` property takes the same values as the
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
margin-inline-end = 
  <'margin-top'>  
```

Examples
--------

### Setting inline end margin

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
  margin-inline-end: 20px;
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

`margin-inline-end`

692

7979

413

No

5615

12.13

872

6918

414

4814

12.23

10.01.0

See also
--------

- [](css_logical_properties_and_values.md)
- [`margin-inline-start`](margin-inline-start.md)
- The mapped physical properties: [`margin-top`](margin-top.md),
    [`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md),
    and [`margin-left`](margin-left.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-end>

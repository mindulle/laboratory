margin-inline-start
===================

The `margin-inline-start`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical inline start margin of an element, which maps to a physical
margin depending on the element\'s writing mode, directionality, and
text orientation. It corresponds to the [`margin-top`](margin-top.md),
[`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md), or
[`margin-left`](margin-left.md) property depending on the values defined
for [`writing-mode`](writing-mode.md), [`direction`](direction.md), and
[`text-orientation`](text-orientation.md).

Try it
------

Syntax
------

[css]

```css
/* <length> values */
margin-inline-start: 10px; /* An absolute length */
margin-inline-start: 1em; /* relative to the text size */
margin-inline-start: 5%; /* relative to the nearest block container's width */

/* Keyword values */
margin-inline-start: auto;

/* Global values */
margin-inline-start: inherit;
margin-inline-start: initial;
margin-inline-start: revert;
margin-inline-start: revert-layer;
margin-inline-start: unset;
```

It relates to [`margin-block-start`](margin-block-start.md),
[`margin-block-end`](margin-block-end.md), and
[`margin-inline-end`](margin-inline-end.md), which define the other margins
of the element.

### Values

The `margin-inline-start` property takes the same values as the
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
margin-inline-start = 
  <'margin-top'>  
```

Examples
--------

### Setting inline start margin

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
  margin-inline-start: 20px;
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

`margin-inline-start`

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
- [`margin-inline-end`](margin-inline-end.md)
- The mapped physical properties: [`margin-top`](margin-top.md),
    [`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md),
    and [`margin-left`](margin-left.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-inline-start>

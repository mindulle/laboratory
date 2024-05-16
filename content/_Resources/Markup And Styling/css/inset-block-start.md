inset-block-start
=================

The `inset-block-start`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the logical block start offset of an element, which maps to a physical
inset depending on the element\'s writing mode, directionality, and text
orientation. It corresponds to the [`top`](top.md), [`right`](right.md),
[`bottom`](bottom.md), or [`left`](left.md) property depending on the values
defined for [`writing-mode`](writing-mode.md), [`direction`](direction.md),
and [`text-orientation`](text-orientation.md).

Try it
------

Syntax
------

[css]

```css
/* <length> values */
inset-block-start: 3px;
inset-block-start: 2.4em;

/* <percentage>s of the width or height of the containing block */
inset-block-start: 10%;

/* Keyword value */
inset-block-start: auto;

/* Global values */
inset-block-start: inherit;
inset-block-start: initial;
inset-block-start: revert;
inset-block-start: revert-layer;
inset-block-start: unset;
```

### Values

The `inset-block-start` property takes the same values as the
[`left`](left.md) property.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         positioned elements
  [Inherited](inheritance.md)           no
  Percentages                        logical-height of containing block
  [Computed value](computed_value.md)   same as box offsets: [`top`](top.md), [`right`](right.md), [`bottom`](bottom.md), [`left`](left.md) properties except that directions are logical
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
inset-block-start = 
  auto                 |
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting block start offset

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
  position: relative;
  inset-block-start: 20px;
  background-color: #c8c800;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  position-properties]](https://drafts.csswg.org/css-logical/#position-properties)

  ------------------------------------------------------------------------------------------

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

`inset-block-start`

87

87

6341--63

No

73

14.1

87

87

6341--63

62

14.5

14.0

See also
--------

- The properties which defines other insets:
    [`inset-block-end`](inset-block-end.md),
    [`inset-inline-start`](inset-inline-start.md), and
    [`inset-inline-end`](inset-inline-end.md)
- The mapped physical properties: [`top`](top.md), [`right`](right.md),
    [`bottom`](bottom.md), and [`left`](left.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/inset-block-start>

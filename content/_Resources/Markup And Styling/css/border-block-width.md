border-block-width
==================

The `border-block-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the width of the logical block borders of an element, which maps to a
physical border width depending on the element\'s writing mode,
directionality, and text orientation. It corresponds to the
[`border-top-width`](border-top-width.md) and
[`border-bottom-width`](border-bottom-width.md), or
[`border-left-width`](border-left-width.md), and
[`border-right-width`](border-right-width.md) property depending on the
values defined for [`writing-mode`](writing-mode.md),
[`direction`](direction.md), and [`text-orientation`](text-orientation.md).

Try it
------

The border width in the other dimension can be set with
[`border-inline-width`](border-inline-width.md), which sets
[`border-inline-start-width`](border-inline-start-width.md), and
[`border-inline-end-width`](border-inline-end-width.md).

Syntax
------

[css]

```css
/* <'border-width'> values */
border-block-width: 5px;
border-block-width: thick;

/* Global values */
border-block-width: inherit;
border-block-width: initial;
border-block-width: revert;
border-block-width: revert-layer;
border-block-width: unset;
```

### Values

[`<'border-width'>`](#border-width)

:   The width of the border. See [`border-width`](border-width.md).

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------
  [Initial value](initial_value.md)     `medium`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  Percentages                        logical-width of containing block
  [Computed value](computed_value.md)   absolute length; `0` if the border style is `none` or `hidden`
  Animation type                     by computed value type
  ---------------------------------- ----------------------------------------------------------------

Formal syntax
-------------

```
border-block-width = 
  <'border-top-width'>  
```

Examples
--------

### Border width with vertical text

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
  border: 1px solid blue;
  border-block-width: 5px;
}
```

#### Results

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-border-block-width]](https://drafts.csswg.org/css-logical/#propdef-border-block-width)

  --------------------------------------------------------------------------------------------------------

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

`border-block-width`

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
    [`border-top-width`](border-top-width.md),
    [`border-right-width`](border-right-width.md),
    [`border-bottom-width`](border-bottom-width.md), and
    [`border-left-width`](border-left-width.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-width>

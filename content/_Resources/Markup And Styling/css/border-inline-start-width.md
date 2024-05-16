border-inline-start-width
=========================

The `border-inline-start-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the width of the logical inline-start border of an element, which maps
to a physical border width depending on the element\'s writing mode,
directionality, and text orientation. It corresponds to the
[`border-top-width`](border-top-width.md),
[`border-right-width`](border-right-width.md),
[`border-bottom-width`](border-bottom-width.md), or
[`border-left-width`](border-left-width.md) property depending on the
values defined for [`writing-mode`](writing-mode.md),
[`direction`](direction.md), and [`text-orientation`](text-orientation.md).

Try it
------

Syntax
------

[css]

```css
/* <'border-width'> values */
border-inline-start-width: 5px;
border-inline-start-width: thick;

/* Global values */
border-inline-start-width: inherit;
border-inline-start-width: initial;
border-inline-start-width: revert;
border-inline-start-width: revert-layer;
border-inline-start-width: unset;
```

Related properties are
[`border-block-start-width`](border-block-start-width.md),
[`border-block-end-width`](border-block-end-width.md), and
[`border-inline-end-width`](border-inline-end-width.md), which define the
other border widths of the element.

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
border-inline-start-width = 
  <'border-top-width'>  
```

Examples
--------

### HTML

[html]

```html
<div>
  <p class="exampleText">Example text</p>
</div>
```

### CSS

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
  border-inline-start-width: 5px;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  border-width]](https://drafts.csswg.org/css-logical/#border-width)

  ----------------------------------------------------------------------------

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

`border-inline-start-width`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-start-width>

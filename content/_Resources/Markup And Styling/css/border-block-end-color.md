border-block-end-color
======================

The `border-block-end-color`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the color of the logical block-end border of an element, which maps to a
physical border color depending on the element\'s writing mode,
directionality, and text orientation. It corresponds to the
[`border-top-color`](border-top-color.md),
[`border-right-color`](border-right-color.md),
[`border-bottom-color`](border-bottom-color.md), or
[`border-left-color`](border-left-color.md) property depending on the
values defined for [`writing-mode`](writing-mode.md),
[`direction`](direction.md), and [`text-orientation`](text-orientation.md).

Try it
------

Syntax
------

[css]

```css
border-block-end-color: yellow;
border-block-end-color: #f5f6f7;

/* Global values */
border-block-end-color: inherit;
border-block-end-color: initial;
border-block-end-color: revert;
border-block-end-color: revert-layer;
border-block-end-color: unset;
```

Related properties are
[`border-block-start-color`](border-block-start-color.md),
[`border-inline-start-color`](border-inline-start-color.md), and
[`border-inline-end-color`](border-inline-end-color.md), which define the
other border colors of the element.

### Values

[`<color>`](color_value.md)

:   The color of the border.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `currentcolor`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   computed color
  Animation type                     by computed value type
  ---------------------------------- ------------------------

Formal syntax
-------------

```
border-block-end-color = 
  <'border-top-color'>  
```

Examples
--------

### Border color with vertical text

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
  border: 10px solid blue;
  border-block-end-color: red;
}
```

#### Results

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  border-color]](https://drafts.csswg.org/css-logical/#border-color)

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

`border-block-end-color`

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
    [`border-top-color`](border-top-color.md),
    [`border-right-color`](border-right-color.md),
    [`border-bottom-color`](border-bottom-color.md), or
    [`border-left-color`](border-left-color.md).
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-block-end-color>

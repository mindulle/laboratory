border-inline-color
===================

The `border-inline-color`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the color of the logical inline borders of an element, which maps to a
physical border color depending on the element\'s writing mode,
directionality, and text orientation. It corresponds to the
[`border-top-color`](border-top-color.md) and
[`border-bottom-color`](border-bottom-color.md), or
[`border-right-color`](border-right-color.md) and
[`border-left-color`](border-left-color.md) property depending on the
values defined for [`writing-mode`](writing-mode.md),
[`direction`](direction.md), and [`text-orientation`](text-orientation.md).

Try it
------

The border color in the other dimension can be set with
[`border-block-color`](border-block-color.md) which sets
[`border-block-start-color`](border-block-start-color.md), and
[`border-block-end-color`](border-block-end-color.md).

Syntax
------

[css]

```css
border-inline-color: yellow;
border-inline-color: #f5f6f7;

/* Global values */
border-inline-color: inherit;
border-inline-color: initial;
border-inline-color: revert;
border-inline-color: revert-layer;
border-inline-color: unset;
```

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
border-inline-color = 
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
  border-inline-color: red;
}
```

#### Results

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-border-inline-color]](https://drafts.csswg.org/css-logical/#propdef-border-inline-color)

  ----------------------------------------------------------------------------------------------------------

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

`border-inline-color`

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
- This property maps to the physical border properties:
    [`border-top-color`](border-top-color.md),
    [`border-right-color`](border-right-color.md),
    [`border-bottom-color`](border-bottom-color.md), or
    [`border-left-color`](border-left-color.md).
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-inline-color>

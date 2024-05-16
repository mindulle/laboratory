border-end-end-radius
=====================

The `border-end-end-radius`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
a logical border radius on an element, which maps to a physical border
radius that depends on the element\'s [`writing-mode`](writing-mode.md),
[`direction`](direction.md), and [`text-orientation`](text-orientation.md).
This is useful when building styles to work regardless of the [](text-orientation.md) and [writing mode](css_writing_modes.md).

Try it
------

This property affects the corner between the block-end and the
inline-end sides of the element. For instance, in a `horizontal-tb`
writing mode with `ltr` direction, it corresponds to the
[`border-bottom-right-radius`](border-bottom-right-radius.md) property.

Syntax
------

[css]

```css
/* <length> values */
/* With one value the corner will be a circle */
border-end-end-radius: 10px;
border-end-end-radius: 1em;

/* With two values the corner will be an ellipse */
border-end-end-radius: 1em 2em;

/* Global values */
border-end-end-radius: inherit;
border-end-end-radius: initial;
border-end-end-radius: revert;
border-end-end-radius: revert-layer;
border-end-end-radius: unset;
```

### Values

[`<length-percentage>`](#length-percentage)

:   Denotes the size of the circle radius or the semi-major and
    semi-minor axes of the ellipse. As absolute length it can be
    expressed in any unit allowed by the CSS [`<length>`](length.md) data
    type. Percentages for the horizontal axis refer to the width of the
    box, percentages for the vertical axis refer to the height of the
    box. Negative values are invalid.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements; but User Agents are not required to apply to `table` and `inline-table` elements when [`border-collapse`](border-collapse.md) is `collapse`. The behavior on internal table elements is undefined for the moment.. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the corresponding dimension of the border box
  [Computed value](computed_value.md)   two absolute [`<length>`](length.md)s or [`<percentage>`](percentage.md)s
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-end-end-radius = 
  <'border-top-left-radius'>  
```

Examples
--------

### Border radius with vertical text

#### HTML

[html]

```html
<div>
  <p class="exampleText">Example</p>
</div>
```

#### CSS

[css]

```css
div {
  background-color: rebeccapurple;
  width: 120px;
  height: 120px;
  border-end-end-radius: 10px;
}

.exampleText {
  writing-mode: vertical-rl;
  padding: 10px;
  background-color: #fff;
  border-end-end-radius: 10px;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  border-radius-properties]](https://drafts.csswg.org/css-logical/#border-radius-properties)

  ----------------------------------------------------------------------------------------------------

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

`border-end-end-radius`

89

89

66

No

75

15

89

89

66

63

15

15.0

See also
--------

- [](css_logical_properties_and_values.md)
- The mapped physical property:
    [`border-bottom-right-radius`](border-bottom-right-radius.md)
- [`writing-mode`](writing-mode.md), [`direction`](direction.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-end-end-radius>

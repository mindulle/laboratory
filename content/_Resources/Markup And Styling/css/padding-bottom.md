padding-bottom
==============

The `padding-bottom`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the height of the [](introduction_to_the_css_box_model.md#padding_area) on
the bottom of an element.

Try it
------

An element\'s padding area is the space between its content and its
border.

**Note:** The [`padding`](padding.md) property can be used to set paddings
on all four sides of an element with a single declaration.

Syntax
------

[css]

```css
/* <length> values */
padding-bottom: 0.5em;
padding-bottom: 0;
padding-bottom: 2cm;

/* <percentage> value */
padding-bottom: 10%;

/* Global values */
padding-bottom: inherit;
padding-bottom: initial;
padding-bottom: revert;
padding-bottom: revert-layer;
padding-bottom: unset;
```

The `padding-bottom` property is specified as a single value chosen from
the list below. Unlike margins, negative values are not allowed for
padding.

### Values

[`<length>`](length.md)

:   The size of the padding as a fixed value. Must be nonnegative.

[`<percentage>`](percentage.md)

:   The size of the padding as a percentage, relative to the inline size
    (*width* in a horizontal language, defined by
    [`writing-mode`](writing-mode.md)) of the [](containing_block.md). Must be nonnegative.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements, except `table-row-group`, `table-header-group`, `table-footer-group`, `table-row`, `table-column-group` and `table-column`. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   the percentage as specified or the absolute length
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
padding-bottom = 
  <length-percentage [0,∞]>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting padding bottom with pixels and percentages

[css]

```css
.content {
  padding-bottom: 5%;
}
.sidebox {
  padding-bottom: 10px;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------

  [CSS Box Model Module Level 3\
  [\#
  padding-physical]](https://drafts.csswg.org/css-box/#padding-physical)

  --------------------------------------------------------------------------------

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

`padding-bottom`

1

12

1

4

3.5

1

≤37

18

4

14

1

1.0

See also
--------

- [](introduction_to_the_css_box_model.md)
- [`padding-top`](padding-top.md), [`padding-right`](padding-right.md),
    [`padding-left`](padding-left.md) and the [`padding`](padding.md)
    shorthand
- The mapped logical properties:
    [`padding-block-start`](padding-block-start.md),
    [`padding-block-end`](padding-block-end.md),
    [`padding-inline-start`](padding-inline-start.md), and
    [`padding-inline-end`](padding-inline-end.md) and the shorthands
    [`padding-block`](padding-block.md) and
    [`padding-inline`](padding-inline.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/padding-bottom>

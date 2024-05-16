padding-top
===========

The `padding-top`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the height of the [](introduction_to_the_css_box_model.md#padding_area) on
the top of an element.

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
padding-top: 0.5em;
padding-top: 0;
padding-top: 2cm;

/* <percentage> value */
padding-top: 10%;

/* Global values */
padding-top: inherit;
padding-top: initial;
padding-top: revert;
padding-top: revert-layer;
padding-top: unset;
```

The `padding-top` property is specified as a single value chosen from
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
padding-top = 
  <length-percentage [0,∞]>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting top padding using pixels and percentages

[css]

```css
.content {
  padding-top: 5%;
}
.sidebox {
  padding-top: 10px;
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

`padding-top`

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
- [`padding-right`](padding-right.md),
    [`padding-bottom`](padding-bottom.md), [`padding-left`](padding-left.md)
    and the [`padding`](padding.md) shorthand
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
https://developer.mozilla.org/en-US/docs/Web/CSS/padding-top>

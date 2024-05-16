margin-right
============

The `margin-right`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the [](introduction_to_the_css_box_model.md#margin_area) on
the right side of an element. A positive value places it farther from
its neighbors, while a negative value places it closer.

Try it
------

The vertical margins of two adjacent boxes may fuse. This is called
[*margin collapsing*](mastering_margin_collapsing.md).

Syntax
------

[css]

```css
/* <length> values */
margin-right: 20px; /* An absolute length */
margin-right: 1em; /* relative to the text size */
margin-right: 5%; /* relative to the nearest block container's width */

/* Keyword values */
margin-right: auto;

/* Global values */
margin-right: inherit;
margin-right: initial;
margin-right: revert;
margin-right: revert-layer;
margin-right: unset;
```

The `margin-right` property is specified as the keyword `auto`, or a
`<length>`, or a `<percentage>`. Its value can be positive, zero, or
negative.

### Values

[`<length>`](length.md)

:   The size of the margin as a fixed value.

[`<percentage>`](percentage.md)

:   The size of the margin as a percentage, relative to the inline size
    (*width* in a horizontal language, defined by
    [`writing-mode`](writing-mode.md)) of the [](containing_block.md).

[`auto`](#auto)

:   The right margin receives a share of the unused horizontal space, as
    determined mainly by the layout mode that is used. If the values of
    `margin-left` and `margin-right` are both `auto`, the calculated
    space is evenly distributed. This table summarizes the different
    cases:

      Value of [`display`](display)                                                                       Value of [`float`](float)   Value of [`position`](position)   Computed value of `auto`                                                                                                                                                         Comment
      --------------------------------------------------------------------------------------------------- --------------------------- --------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------------------
      `inline`, `inline-block`, `inline-table`                                                            *any*                       `static` or `relative`            `0`                                                                                                                                                                              Inline layout mode
      `block`, `inline`, `inline-block`, `block`, `table`, `inline-table`, `list-item`, `table-caption`   *any*                       `static` or `relative`            `0`, except if both `margin-left` and `margin-right` are set to `auto`. In this case, it is set to the value centering the element inside its parent.                            Block layout mode
      `block`, `inline`, `inline-block`, `block`, `table`, `inline-table`, `list-item`, `table-caption`   `left` or `right`           `static` or `relative`            `0`                                                                                                                                                                              Block layout mode (floating element)
      *any* `table-*`*, except* `table-caption`                                                           *any*                       *any*                             `0`                                                                                                                                                                              Internal `table-*` elements don\'t have margins, use [`border-spacing`](border-spacing) instead
      *any, except `flex`,* `inline-flex`*, or* `table-*`                                                 *any*                       *`fixed`* or `absolute`           `0`, except if both `margin-left` and `margin-right` are set to `auto`. In this case, it is set to the value centering the border area inside the available `width`, if fixed.   Absolutely positioned layout mode
      `flex`, `inline-flex`                                                                               *any*                       *any*                             `0`, except if there is any positive horizontal free space. In this case, it is evenly distributed to all horizontal `auto` margins.                                             Flexbox layout mode

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements, except elements with table [`display`](display.md) types other than `table-caption`, `table` and `inline-table`. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   the percentage as specified or the absolute length
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
margin-right = 
  <length-percentage>  |
  auto                 

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting right margin using pixels and percentages

[css]

```css
.content {
  margin-right: 5%;
}
.sidebox {
  margin-right: 10px;
}
.logo {
  margin-right: -5px;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Box Model Module Level 3\
  [\#
  margin-physical]](https://drafts.csswg.org/css-box/#margin-physical)

  ------------------------------------------------------------------------------

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

`margin-right`

1

12

1

3

3.5

1

4.4

18

4

10.1

1

1.0

`auto`

1

12The `auto` value is not supported in quirks mode.

1

6The `auto` value is not supported in quirks mode.

3.5

1

37

18

4

14

1

1.0

See also
--------

- [`margin-top`](margin-top.md), [`margin-bottom`](margin-bottom.md), and
    [`margin-left`](margin-left.md) and the [`margin`](margin.md) shorthand
- The mapped logical properties:
    [`margin-block-start`](margin-block-start.md),
    [`margin-block-end`](margin-block-end.md),
    [`margin-inline-start`](margin-inline-start.md), and
    [`margin-inline-end`](margin-inline-end.md) and the shorthands
    [`margin-block`](margin-block.md) and [`margin-inline`](margin-inline.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right>

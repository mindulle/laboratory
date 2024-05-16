margin-top
==========

The `margin-top` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the [](introduction_to_the_css_box_model.md#margin_area) on
the top of an element. A positive value places it farther from its
neighbors, while a negative value places it closer.

Try it
------

This property has no effect on *non-[replaced](replaced_element.md)* inline
elements, such as
[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)
or
[`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code).

Syntax
------

[css]

```css
/* <length> values */
margin-top: 10px; /* An absolute length */
margin-top: 1em; /* relative to the text size */
margin-top: 5%; /* relative to the nearest block container's width */

/* Keyword values */
margin-top: auto;

/* Global values */
margin-top: inherit;
margin-top: initial;
margin-top: revert;
margin-top: revert-layer;
margin-top: unset;
```

The `margin-top` property is specified as the keyword `auto`, or a
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

:   The browser selects a suitable value to use. See [`margin`](margin.md).

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
margin-top = 
  <length-percentage>  |
  auto                 

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting positive and negative top margins

[css]

```css
.content {
  margin-top: 5%;
}
.sidebox {
  margin-top: 10px;
}
.logo {
  margin-top: -5px;
}
#footer {
  margin-top: 1em;
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

`margin-top`

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

- [`margin-right`](margin-right.md), [`margin-bottom`](margin-bottom.md),
    and [`margin-left`](margin-left.md) and the [`margin`](margin.md)
    shorthand
- The mapped logical properties:
    [`margin-block-start`](margin-block-start.md),
    [`margin-block-end`](margin-block-end.md),
    [`margin-inline-start`](margin-inline-start.md), and
    [`margin-inline-end`](margin-inline-end.md) and the shorthands
    [`margin-block`](margin-block.md) and [`margin-inline`](margin-inline.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top>

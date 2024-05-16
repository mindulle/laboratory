margin
======

The `margin` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
shorthand property sets the [](introduction_to_the_css_box_model.md#margin_area) on
all four sides of an element.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`margin-top`](margin-top.md)
- [`margin-right`](margin-right.md)
- [`margin-bottom`](margin-bottom.md)
- [`margin-left`](margin-left.md)

Syntax
------

[css]

```css
/* Apply to all four sides */
margin: 1em;
margin: -3px;

/* top and bottom | left and right */
margin: 5% auto;

/* top | left and right | bottom */
margin: 1em auto 2em;

/* top | right | bottom | left */
margin: 2px 1em 0 auto;

/* Global values */
margin: inherit;
margin: initial;
margin: revert;
margin: revert-layer;
margin: unset;
```

The `margin` property may be specified using one, two, three, or four
values. Each value is a [`<length>`](length.md), a
[`<percentage>`](percentage.md), or the keyword `auto`. Negative values
draw the element closer to its neighbors than it would be by default.

- When **one** value is specified, it applies the same margin to **all
    four sides**.
- When **two** values are specified, the first margin applies to the
    **top and bottom**, the second to the **left and right**.
- When **three** values are specified, the first margin applies to the
    **top**, the second to the **right and left**, the third to the
    **bottom**.
- When **four** values are specified, the margins apply to the
    **top**, **right**, **bottom**, and **left** in that order
    (clockwise).

### Values

[`<length>`](length.md)

:   The size of the margin as a fixed value.

[`<percentage>`](percentage.md)

:   The size of the margin as a percentage, relative to the inline size
    (*width* in a horizontal language, defined by
    [`writing-mode`](writing-mode.md)) of the [](containing_block.md).

[`auto`](#auto)

:   The browser selects a suitable margin to use. For example, in
    certain cases this value can be used to center an element.

Description
-----------

This property can be used to set a margin on all four sides of an
element. Margins create extra space *around* an element, unlike
[`padding`](padding.md), which creates extra space *within* an element.

The top and bottom margins have no effect on
*non-[replaced](replaced_element.md)* inline elements, such as
[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)
or
[`<code>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/code).

### Horizontal centering

To center something horizontally in modern browsers, you can use
[`display`](display.md)`: flex;`
[`justify-content`](justify-content.md)`: center;`.

However, in older browsers like IE8-9 that do not support Flexible Box
Layout, these are not available. In order to center an element inside
its parent, use `margin: 0 auto;`.

### Margin collapsing

Elements\' top and bottom margins are sometimes collapsed into a single
margin that is equal to the larger of the two margins. See [](mastering_margin_collapsing.md) for more
information.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`margin-bottom`](margin-bottom.md): |
|                                   |     `0`                           |
|                                   | -   [`margin-left`](margin-left.md): |
|                                   |     `0`                           |
|                                   | -                                 |
|                                   |   [`margin-right`](margin-right.md): |
|                                   |     `0`                           |
|                                   | -   [`margin-top`](margin-top.md):   |
|                                   |     `0`                           |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements, except elements     |
|                                   | with table [`display`](display.md)   |
|                                   | types other than `table-caption`, |
|                                   | `table` and `inline-table`. It    |
|                                   | also applies to                   |
|                                   | [                                 |
|                                   | `::first-letter`](::first-letter) |
|                                   | and                               |
|                                   | [`::first-line`](::first-line).   |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | refer to the width of the         |
|                                   | containing block                  |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`margin-bottom`](margin-bottom.md): |
|                                   |     the percentage as specified   |
|                                   |     or the absolute length        |
|                                   | -   [`margin-left`](margin-left.md): |
|                                   |     the percentage as specified   |
|                                   |     or the absolute length        |
|                                   | -                                 |
|                                   |   [`margin-right`](margin-right.md): |
|                                   |     the percentage as specified   |
|                                   |     or the absolute length        |
|                                   | -   [`margin-top`](margin-top.md):   |
|                                   |     the percentage as specified   |
|                                   |     or the absolute length        |
+-----------------------------------+-----------------------------------+
| Animation type                    | a [length](length.md#interpolation)  |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
margin = 
  <'margin-top'>  
```

Examples
--------

### Simple example

#### HTML

[html]

```html
<div class="center">This element is centered.</div>

<div class="outside">This element is positioned outside of its container.</div>
```

#### CSS

[css]

```css
.center {
  margin: auto;
  background: lime;
  width: 66%;
}

.outside {
  margin: 3rem 0 0 -3rem;
  background: cyan;
  width: 66%;
}
```

### More examples

[css]

```css
margin: 5%; /* All sides: 5% margin */

margin: 10px; /* All sides: 10px margin */

margin: 1.6em 20px; /* top and bottom: 1.6em margin */
/* left and right: 20px margin */

margin: 10px 3% -1em; /* top:            10px margin */
/* left and right: 3% margin   */
/* bottom:         -1em margin */

margin: 10px 3px 30px 5px; /* top:    10px margin */
/* right:  3px margin  */
/* bottom: 30px margin */
/* left:   5px margin  */

margin: 2em auto; /* top and bottom: 2em margin   */
/* Box is horizontally centered */

margin: auto; /* top and bottom: 0 margin     */
/* Box is horizontally centered */
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Box Model Module Level 3\
  [\# margin]](https://drafts.csswg.org/css-box/#margin)

  -----------------------------------------------------------------------

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

`margin`

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

- [](introduction_to_the_css_box_model.md)
- [Margin collapsing](mastering_margin_collapsing.md)
- [`margin-top`](margin-top.md), [`margin-right`](margin-right.md),
    [`margin-bottom`](margin-bottom.md), and [`margin-left`](margin-left.md)
- The mapped logical properties:
    [`margin-block-start`](margin-block-start.md),
    [`margin-block-end`](margin-block-end.md),
    [`margin-inline-start`](margin-inline-start.md), and
    [`margin-inline-end`](margin-inline-end.md) and the shorthands
    [`margin-block`](margin-block.md) and [`margin-inline`](margin-inline.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/margin>

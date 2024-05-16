grid-row
========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `grid-row` CSS [shorthand property](shorthand_properties.md) specifies
a grid item\'s size and location within a [grid
row](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Row) by
contributing a line, a span, or nothing (automatic) to its grid
placement, thereby specifying the inline-start and inline-end edge of
its [grid
area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`grid-row-end`](grid-row-end.md)
- [`grid-row-start`](grid-row-start.md)

Syntax
------

[css]

```css
/* Keyword values */
grid-row: auto;
grid-row: auto / auto;

/* <custom-ident> values */
grid-row: somegridarea;
grid-row: somegridarea / someothergridarea;

/* <integer> + <custom-ident> values */
grid-row: somegridarea 4;
grid-row: 4 somegridarea / 6;

/* span + <integer> + <custom-ident> values */
grid-row: span 3;
grid-row: span somegridarea;
grid-row: 5 somegridarea span;
grid-row: span 3 / 6;
grid-row: span somegridarea / span someothergridarea;
grid-row: 5 somegridarea span / 2 span;

/* Global values */
grid-row: inherit;
grid-row: initial;
grid-row: revert;
grid-row: revert-layer;
grid-row: unset;
```

This property is specified as one or two `<grid-line>` values.

If two `<grid-line>` values are given, they are separated by `/`. The
`grid-row-start` longhand is set to the value before the slash, and the
`grid-row-end` longhand is set to the value after the slash.

Each `<grid-line>` value can be specified as:

- either the `auto` keyword
- or a `<custom-ident>` value
- or an `<integer>` value
- or both `<custom-ident>` and `<integer>`, separated by a space
- or the keyword `span` together with either a `<custom-ident>` or an
    `<integer>` or both.

### Values

[`auto`](#auto)

:   Is a keyword indicating that the property contributes nothing to the
    grid item\'s placement, indicating auto-placement, an automatic
    span, or a default span of `1`.

[`<custom-ident>`](#custom-ident)

:   If there is a named line with the name
    `<custom-ident>-start`/`<custom-ident>-end`, it contributes the
    first such line to the grid item\'s placement.

    **Note:** Named grid areas automatically generate implicit named
    lines of this form, so specifying `grid-row: foo;` will choose the
    start/end edge of that named grid area (unless another line named
    `foo-start`/`foo-end` was explicitly specified before it).
    

    Otherwise, this is treated as if the integer `1` had been specified
    along with the `<custom-ident>`.

[`<integer> && <custom-ident>?`](#integer_custom-ident)

:   Contributes the nth grid line to the grid item\'s placement. If a
    negative integer is given, it instead counts in reverse, starting
    from the end edge of the explicit grid.

    If a name is given as a `<custom-ident>`, only lines with that name
    are counted. If not enough lines with that name exist, all implicit
    grid lines are assumed to have that name for the purpose of finding
    this position.

    An [`<integer>`](integer) value of `0` is invalid.

[`span && [ <integer> || <custom-ident> ]`](#span_integer_custom-ident_)

:   Contributes a grid span to the grid item\'s placement such that the
    corresponding edge of the grid item\'s grid area is n lines from the
    opposite edge.

    If a name is given as a `<custom-ident>`, only lines with that name
    are counted. If not enough lines with that name exist, all implicit
    grid lines on the side of the explicit grid corresponding to the
    search direction are assumed to have that name for the purpose of
    counting this span.

    If the `<integer>` is omitted, it defaults to `1`. Negative integers
    or 0 are invalid.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](grid-row-start.md): |
|                                   |     `auto`                        |
|                                   | -                                 |
|                                   |   [`grid-row-end`](grid-row-end.md): |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | grid items and                    |
|                                   | absolutely-positioned boxes whose |
|                                   | containing block is a grid        |
|                                   | container                         |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](grid-row-start.md): |
|                                   |     as specified                  |
|                                   | -                                 |
|                                   |   [`grid-row-end`](grid-row-end.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | discrete                          |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
grid-row = 
  <grid-line> [ / <grid-line> ]?  
```

Examples
--------

### Setting grid row size and location

#### HTML

[html]

```html
<div id="grid">
  <div id="item1"></div>
  <div id="item2"></div>
  <div id="item3"></div>
</div>
```

#### CSS

[css]

```css
#grid {
  display: grid;
  height: 200px;
  grid-template-columns: 200px;
  grid-template-rows: repeat(6, 1fr);
}

#item1 {
  background-color: lime;
}

#item2 {
  background-color: yellow;
  grid-row: 2 / 4;
}

#item3 {
  background-color: blue;
  grid-row: span 2 / 7;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  placement-shorthands]](https://drafts.csswg.org/css-grid/#placement-shorthands)

  -----------------------------------------------------------------------------------------

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

`grid-row`

57

16

52

No

44

10.1

57

57

52

43

10.3

6.0

See also
--------

- Related CSS properties: [`grid-row-start`](grid-row-start.md),
    [`grid-row-end`](grid-row-end.md), [`grid-column`](grid-column.md),
    [`grid-column-start`](grid-column-start.md),
    [`grid-column-end`](grid-column-end.md)
- Grid Layout Guide: *[](grid_layout_using_line-based_placement.md)*
- Video tutorial: *[Line-based
    placement](https://gridbyexample.com/video/series-line-based-placement/)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row>

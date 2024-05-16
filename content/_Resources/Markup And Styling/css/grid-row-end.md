grid-row-end
============

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `grid-row-end` CSS property specifies a grid item\'s end position
within the grid row by contributing a line, a span, or nothing
(automatic) to its grid placement, thereby specifying the inline-end
edge of its [grid
area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
grid-row-end: auto;

/* <custom-ident> values */
grid-row-end: somegridarea;

/* <integer> + <custom-ident> values */
grid-row-end: 2;
grid-row-end: somegridarea 4;

/* span + <integer> + <custom-ident> values */
grid-row-end: span 3;
grid-row-end: span somegridarea;
grid-row-end: 5 somegridarea span;

/* Global values */
grid-row-end: inherit;
grid-row-end: initial;
grid-row-end: revert;
grid-row-end: revert-layer;
grid-row-end: unset;
```

### Values

[`auto`](#auto)

:   Is a keyword indicating that the property contributes nothing to the
    grid item\'s placement, indicating auto-placement, an automatic
    span, or a default span of `1`.

[`<custom-ident>`](#custom-ident)

:   If there is a named line with the name \'\<custom-ident\>-end\', it
    contributes the first such line to the grid item\'s placement.

    **Note:** Named grid areas automatically generate implicit named
    lines of this form, so specifying `grid-row-end: foo;` will choose
    the end edge of that named grid area (unless another line named
    `foo-end` was explicitly specified before it).
    

    Otherwise, this is treated as if the integer `1` had been specified
    along with the `<custom-ident>`.

    The `<custom-ident>` cannot take the `span` value.

[`<integer> && <custom-ident>?`](#integer_custom-ident)

:   Contributes the nth grid line to the grid item\'s placement. If a
    negative integer is given, it instead counts in reverse, starting
    from the end edge of the explicit grid.

    If a name is given as a \<custom-ident\>, only lines with that name
    are counted. If not enough lines with that name exist, all implicit
    grid lines are assumed to have that name for the purpose of finding
    this position.

    An [`<integer>`](integer) value of `0` is invalid.

[`span && [ <integer> || <custom-ident> ]`](#span_integer_custom-ident_)

:   Contributes a grid span to the grid item\'s placement such that the
    row end edge of the grid item\'s grid area is n lines from the start
    edge.

    If a name is given as a \<custom-ident\>, only lines with that name
    are counted. If not enough lines with that name exist, all implicit
    grid lines on the side of the explicit grid corresponding to the
    search direction are assumed to have that name for the purpose of
    counting this span.

    If the \<integer\> is omitted, it defaults to `1`. Negative integers
    or 0 are invalid.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         grid items and absolutely-positioned boxes whose containing block is a grid container
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------

Formal syntax
-------------

```
grid-row-end = 
  <grid-line>  
```

Examples
--------

### Setting row end for a grid item

#### HTML

[html]

```html
<div class="wrapper">
  <div class="box1">One</div>
  <div class="box2">Two</div>
  <div class="box3">Three</div>
  <div class="box4">Four</div>
  <div class="box5">Five</div>
</div>
```

#### CSS

[css]

```css
.wrapper {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 100px;
}

.box1 {
  grid-column-start: 1;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 3;
}

.box2 {
  grid-column-start: 1;
  grid-row-start: 3;
  grid-row-end: 5;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  line-placement]](https://drafts.csswg.org/css-grid/#line-placement)

  -----------------------------------------------------------------------------

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

`grid-row-end`

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
    [`grid-row`](grid-row.md), [`grid-column-start`](grid-column-start.md),
    [`grid-column-end`](grid-column-end.md), [`grid-column`](grid-column.md)
- Grid Layout Guide: *[](grid_layout_using_line-based_placement.md)*
- Video tutorial: *[Line-based
    placement](https://gridbyexample.com/video/series-line-based-placement/)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/grid-row-end>

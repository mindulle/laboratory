# grid-area

## Baseline: [Widely supported]

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
  more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `grid-area` CSS [shorthand property](shorthand_properties.md) specifies
a grid item\'s size and location within a
[grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid) by
contributing a line, a span, or nothing (automatic) to its grid
placement, thereby specifying the edges of its [grid
area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

## Try it

If four `<grid-line>` values are specified, `grid-row-start` is set to
the first value, `grid-column-start` is set to the second value,
`grid-row-end` is set to the third value, and `grid-column-end` is set
to the fourth value.

When `grid-column-end` is omitted, if `grid-column-start` is a
[`<custom-ident>`](custom-ident.md), `grid-column-end` is set to that
`<custom-ident>`; otherwise, it is set to `auto`.

When `grid-row-end` is omitted, if `grid-row-start` is a
`<custom-ident>`, `grid-row-end` is set to that `<custom-ident>`;
otherwise, it is set to `auto`.

When `grid-column-start` is omitted, if `grid-row-start` is a
`<custom-ident>`, all four longhands are set to that value. Otherwise,
it is set to `auto`.

The grid-area property can also be set to a
[`<custom-ident>`](custom-ident.md) which acts as a name for the area,
which can then be placed using
[`grid-template-areas`](grid-template-areas.md).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`grid-row-start`](grid-row-start.md)
- [`grid-column-start`](grid-column-start.md)
- [`grid-row-end`](grid-row-end.md)
- [`grid-column-end`](grid-column-end.md)

## Syntax

[css]

```css
/* Keyword values */
grid-area: auto;
grid-area: auto / auto;
grid-area: auto / auto / auto;
grid-area: auto / auto / auto / auto;

/* <custom-ident> values */
grid-area: some-grid-area;
grid-area: some-grid-area / another-grid-area;

/* <integer> && <custom-ident>? values */
grid-area: 4 some-grid-area;
grid-area: 4 some-grid-area / 2 another-grid-area;

/* span && [ <integer> || <custom-ident> ] values */
grid-area: span 3;
grid-area: span 3 / span some-grid-area;
grid-area: 2 span / another-grid-area span;

/* Global values */
grid-area: inherit;
grid-area: initial;
grid-area: revert;
grid-area: revert-layer;
grid-area: unset;
```

### Values

[`auto`](#auto)

: Is a keyword indicating that the property contributes nothing to the
grid item\'s placement, indicating auto-placement or a default span
of `1`.

[`<custom-ident>`](#custom-ident)

: If there is a named line with the name
\'`<custom-ident>-start`\'/\'`<custom-ident>-end`\', it contributes
the first such line to the grid item\'s placement.

    **Note:** Named grid areas automatically generate implicit named
    lines of this form, so specifying `grid-area: foo;` will choose the
    start/end edge of that named grid area (unless another line named
    `foo-start`/`foo-end` was explicitly specified before it).


    Otherwise, this is treated as if the integer `1` had been specified
    along with the `<custom-ident>`.

[`<integer> && <custom-ident>?`](#integer_custom-ident)

: Contributes the n-th grid line to the grid item\'s placement. If a
negative integer is given, it instead counts in reverse, starting
from the end edge of the explicit grid.

    If a name is given as a [`<custom-ident>`](custom-ident), only lines
    with that name are counted. If not enough lines with that name
    exist, all implicit grid lines are assumed to have that name for the
    purpose of finding this position.

    An [`<integer>`](integer) value of `0` is invalid.

[`span && [ <integer> || <custom-ident> ]`](#span_integer_custom-ident_)

: Contributes a grid span to the grid item\'s placement such that the
corresponding edge of the grid item\'s grid area is _n_ lines from
the opposite edge.

    If a name is given as a [`<custom-ident>`](custom-ident), only lines
    with that name are counted. If not enough lines with that name
    exist, all implicit grid lines on the side of the explicit grid
    corresponding to the search direction are assumed to have that name
    for the purpose of counting this span.

    If the [`<integer>`](integer) is omitted, it defaults to `1`.
    Negative integers or 0 are invalid.

## Formal definition

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md) | as each of the properties of the |
| | shorthand:\ |
| | |
| | - [](grid-row-start.md): |
| | `auto` |
| | - [](grid-column-start.md): |
| | `auto` |
| | - |
| | [`grid-row-end`](grid-row-end.md): |
| | `auto` |
| | - [](grid-column-end.md): |
| | `auto` |
+-----------------------------------+-----------------------------------+
| Applies to | grid items and |
| | absolutely-positioned boxes whose |
| | containing block is a grid |
| | container |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md) | no |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md) | as each of the properties of the |
| | shorthand:\ |
| | |
| | - [](grid-row-start.md): |
| | as specified |
| | - [](grid-column-start.md): |
| | as specified |
| | - |
| | [`grid-row-end`](grid-row-end.md): |
| | as specified |
| | - [](grid-column-end.md): |
| | as specified |
+-----------------------------------+-----------------------------------+
| Animation type | discrete |
+-----------------------------------+-----------------------------------+

## Formal syntax

```
grid-area =
  <grid-line> [ / <grid-line> ]
```

## Examples

### Setting grid areas

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
  height: 100px;
  grid-template: repeat(4, 1fr) / 50px 100px;
}

#item1 {
  background-color: lime;
  grid-area: 2 / 2 / auto / span 3;
}

#item2 {
  background-color: yellow;
}

#item3 {
  background-color: blue;
}
```

#### Result

## Specifications

---

Specification

---

[CSS Grid Layout Module Level 2\
 [\#
propdef-grid-area]](https://drafts.csswg.org/css-grid/#propdef-grid-area)

---

## Browser compatibility

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

`grid-area`

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

## See also

- Related CSS properties: [`grid-row`](grid-row.md),
  [`grid-row-start`](grid-row-start.md), [`grid-row-end`](grid-row-end.md),
  [`grid-column`](grid-column.md),
  [`grid-column-start`](grid-column-start.md),
  [`grid-column-end`](grid-column-end.md),
  [`grid-template-areas`](grid-template-areas.md)
- Grid Layout Guide: _[](grid_template_areas.md)_
- Video tutorial: _[Grid Template
  Areas](https://gridbyexample.com/video/grid-template-areas/)_

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/grid-area>

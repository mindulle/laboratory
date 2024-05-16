visibility
==========

The `visibility` CSS property shows or hides an element without changing
the layout of a document. The property can also hide rows or columns in
a
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table).

Try it
------

To both hide an element *and remove it from the document layout*, set
the [`display`](display.md) property to `none` instead of using
`visibility`.

Syntax
------

[css]

```css
/* Keyword values */
visibility: visible;
visibility: hidden;
visibility: collapse;

/* Global values */
visibility: inherit;
visibility: initial;
visibility: revert;
visibility: revert-layer;
visibility: unset;
```

The `visibility` property is specified as one of the keyword values
listed below.

### Values

[`visible`](#visible)

:   The element box is visible.

[`hidden`](#hidden)

:   The element box is invisible (not drawn), but still affects layout
    as normal. Descendants of the element will be visible if they have
    `visibility` set to `visible`. The element cannot receive focus
    (such as when navigating through [tab
    indexes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/tabindex)).

[`collapse`](#collapse)

:   The `collapse` keyword has different effects for different elements:

    -   For
        [`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
        rows, columns, column groups, and row groups, the row(s) or
        column(s) are hidden and the space they would have occupied is
        removed (as if `display`: none were applied to the column/row of
        the table). However, the size of other rows and columns is still
        calculated as though the cells in the collapsed row(s) or
        column(s) are present. This value allows for the fast removal of
        a row or column from a table without forcing the recalculation
        of widths and heights for the entire table.
    -   Collapsed flex items and ruby annotations are hidden, and the
        space they would have occupied is removed.
    -   For other elements, `collapse` is treated the same as `hidden`.

Accessibility concerns
----------------------

Using a `visibility` value of `hidden` on an element will remove it from
the [accessibility
tree](https://developer.mozilla.org/en-US/docs/Learn/Accessibility/What_is_accessibility#accessibility_apis).
This will cause the element and all its descendant elements to no longer
be announced by screen reading technology.

Interpolation
-------------

When animated, visibility values are interpolated between *visible* and
*not-visible*. One of the start or ending values must therefore be
`visible` or no
[interpolation](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
can happen. The value is interpolated as a discrete step, where values
of the easing function between `0` and `1` map to `visible` and other
values of the easing function (which occur only at the start/end of the
transition or as a result of `cubic-bezier()` functions with y values
outside of \[0, 1\]) map to the closer endpoint.

Notes
-----

- Support for `visibility: collapse` is missing or partially incorrect
    in some modern browsers. It may not be correctly treated like
    `visibility: hidden` on elements other than table rows and columns.
- `visibility: collapse` may change the layout of a table if the table
    has nested tables within the cells that are collapsed, unless
    `visibility: visible` is specified explicitly on nested tables.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------
  [Initial value](initial_value.md)     `visible`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     a [visibility](visibility.md#interpolation)
  ---------------------------------- ------------------------------------------

Formal syntax
-------------

```
visibility = 
  visible   |
  hidden    |
  collapse  
```

Examples
--------

### Basic example

#### HTML

[html]

```html
<p class="visible">The first paragraph is visible.</p>
<p class="not-visible">The second paragraph is NOT visible.</p>
<p class="visible">
  The third paragraph is visible. Notice the second paragraph is still occupying
  space.
</p>
```

#### CSS

[css]

```css
.visible {
  visibility: visible;
}

.not-visible {
  visibility: hidden;
}
```

### Table example

#### HTML

[html]

```html
<table>
  <tr>
    <td>1.1</td>
    <td class="collapse">1.2</td>
    <td>1.3</td>
  </tr>
  <tr class="collapse">
    <td>2.1</td>
    <td>2.2</td>
    <td>2.3</td>
  </tr>
  <tr>
    <td>3.1</td>
    <td>3.2</td>
    <td>3.3</td>
  </tr>
</table>
```

#### CSS

[css]

```css
.collapse {
  visibility: collapse;
}

table {
  border: 1px solid red;
}

td {
  border: 1px solid gray;
}
```

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [CSS Display Module Level 3\
  [\#
  visibility]](https://drafts.csswg.org/css-display/#visibility)

  ------------------------------------------------------------------------

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

`visibility`

1

12

1

4\[\"Internet Explorer doesn\'t support `visibility: initial`.\",
\"Internet Explorer doesn\'t support `visibility: unset`.\", \"Up to
Internet Explorer 7, descendants of `hidden` elements will still be
invisible even if they have `visibility` set to `visible`.\"\]

4

1

4.4

18

4

10.1

1

1.0

`collapse`

1\[\"Chrome treats `visibility: collapse` like `hidden`, leaving a white
gap.\", \"Chrome supports the `collapse` value only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

12

1\[\"Firefox doesn\'t hide borders when hiding
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements if `border-collapse: collapse` is set.\", \"Before Firefox 88,
`collapse` is not supported on ruby annotations.\"\]

10

4\[\"Opera treats `visibility: collapse` like `hidden`, leaving a white
gap.\", \"Opera supports the `collapse` value only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

1.3\[\"Safari treats `visibility: collapse` like `hidden`, leaving a
white gap.\", \"Safari supports the collapse value only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

≤37\[\"WebView treats `visibility: collapse` like `hidden`, leaving a
white gap.\", \"WebView supports the `collapse` value only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

18\[\"Chrome treats `visibility: collapse` like `hidden`, leaving a
white gap.\", \"Chrome supports the `collapse` value only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

4\[\"Firefox doesn\'t hide borders when hiding
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements if `border-collapse: collapse` is set.\", \"Before Firefox 88,
`collapse` is not supported on ruby annotations.\"\]

10.1\[\"Opera treats `visibility: collapse` like `hidden`, leaving a
white gap.\", \"Opera supports the `collapse` value only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

1\[\"Safari treats `visibility: collapse` like `hidden`, leaving a white
gap.\", \"Safari supports the collapse value only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

1.0\[\"Samsung Internet treats `visibility: collapse` like `hidden`,
leaving a white gap.\", \"Samsung Internet supports the `collapse` value
only on
[`<tr>`](https://developer.mozilla.org/docs/Web/HTML/Element/tr),
[`<thead>`](https://developer.mozilla.org/docs/Web/HTML/Element/thead),
[`<tbody>`](https://developer.mozilla.org/docs/Web/HTML/Element/tbody),
and
[`<tfoot>`](https://developer.mozilla.org/docs/Web/HTML/Element/tfoot),
but not on
[`<col>`](https://developer.mozilla.org/docs/Web/HTML/Element/col) and
[`<colgroup>`](https://developer.mozilla.org/docs/Web/HTML/Element/colgroup)
elements.\"\]

See also
--------

- [`display`](display.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/visibility>

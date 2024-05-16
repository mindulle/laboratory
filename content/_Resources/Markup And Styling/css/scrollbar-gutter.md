scrollbar-gutter
================

The `scrollbar-gutter`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property allows
authors to reserve space for the scrollbar, preventing unwanted layout
changes as the content grows while also avoiding unnecessary visuals
when scrolling isn\'t needed.

An element\'s *scrollbar gutter* is the space between the inner border
edge and the outer padding edge, where the browser may display a
scrollbar. If no scrollbar is present, the gutter will be painted as an
extension of the padding.

The browser determines whether *classic* scrollbars or *overlay*
scrollbars are used:

- Classic scrollbars are always placed in a gutter, consuming space
    when present.
- Overlay scrollbars are placed over the content, not in a gutter, and
    are usually partially transparent.

Syntax
------

[css]

```css
/* Initial value */
scrollbar-gutter: auto;

/* "stable" keyword, with optional modifier */
scrollbar-gutter: stable;
scrollbar-gutter: stable both-edges;

/* Global values */
scrollbar-gutter: inherit;
scrollbar-gutter: initial;
scrollbar-gutter: revert;
scrollbar-gutter: revert-layer;
scrollbar-gutter: unset;
```

### Values

[`auto`](#auto)

:   The initial value. Classic scrollbars create a gutter when
    `overflow` is `scroll`, or when `overflow` is `auto` and the box is
    overflowing. Overlay scrollbars do not consume space.

[`stable`](#stable)

:   When using classic scrollbars, the gutter will be present if
    `overflow` is `auto`, `scroll`, or `hidden` even if the box is not
    overflowing. When using overlay scrollbars, the gutter will not be
    present.

[`both-edges`](#both-edges)

:   If a gutter would be present on one of the inline start/end edges of
    the box, another will be present on the opposite edge as well.

Formal definition
-----------------

  ---------------------------------- -----------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         scrolling boxes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------

Formal syntax
-------------

```
scrollbar-gutter = 
  auto                   |
  stable && both-edges?  
```

Examples
--------

The examples below show how the different values for the
`scrollbar-gutter` property would affect a scrollable `div` element
(`.container`) with one or more paragraphs contained within.

**Note:** In the images for the examples, the user\'s system settings
are set to classic scrollbars (always shown).

### Example 1

Prevent unneeded layout changes as the content growing or shrinking
causes the scrollbar to appear/disappear, a space is reserved for it.

[css]

```css
.container {
  scrollbar-gutter: stable;
}
```

### Example 2

Add symmetric spacing to both sides of the box so the content is
centered:

[css]

```css
.container {
  scrollbar-gutter: stable both-edges;
}
```

### Example 3

Align the contents of a non-scrolling element and a scrolling one
adjacent to it: This example shows two divs side by side. The one on the
left has no scroll, but the one on the right does. Both have
`scrollbar-gutter` applied, which also reserves space for the div on the
left which doesn\'t have scrollable content. This is a good technique to
use to keep the width of content consistent.

[css]

```css
.container1 {
  overflow: hidden;
  scrollbar-gutter: stable;
}

.container2 {
  scrollbar-gutter: stable;
}
```

### Overlay scrollbars

For reference, this image shows the same div as above, but with the
user\'s system settings set to overlay scrollbars. Note here the
scrollbar will only show when the user is scrolling and on top of the
content, so no space is reserved for it and the `scrollbar-gutter`
property has no effect.

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  scrollbar-gutter-property]](https://drafts.csswg.org/css-overflow/#scrollbar-gutter-property)

  -------------------------------------------------------------------------------------------------------

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

`scrollbar-gutter`

94

94

97

No

80

No

94

94

97

66

No

17.0

See also
--------

- [CSS overflow](css_overflow.md) module
- [CSS scrollbars styling](css_scrollbars_styling.md) module
- [`overflow`](overflow.md)
- [`scrollbar-width`](scrollbar-width.md)
- [`scrollbar-color`](scrollbar-color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scrollbar-gutter>

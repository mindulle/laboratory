page-break-after
================

**Warning:** This property has been replaced by the
[`break-after`](break-after.md) property.

The `page-break-after` CSS property adjusts page breaks *after* the
current element.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
page-break-after: auto;
page-break-after: always;
page-break-after: avoid;
page-break-after: left;
page-break-after: right;
page-break-after: recto;
page-break-after: verso;

/* Global values */
page-break-after: inherit;
page-break-after: initial;
page-break-after: revert;
page-break-after: revert-layer;
page-break-after: unset;
```

This property applies to block elements that generate a box. It won\'t
apply on an empty
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
that won\'t generate a box.

### Values

[`auto`](#auto)

:   Initial value. Automatic page breaks (neither forced nor forbidden).

[`always`](#always)

:   Always force page breaks after the element.

[`avoid`](#avoid)

:   Avoid page breaks after the element.

[`left`](#left)

:   Force page breaks after the element so that the next page is
    formatted as a left page. It\'s the page placed on the left side of
    the spine of the book or the back side of the page in duplex
    printing.

[`right`](#right)

:   Force page breaks after the element so that the next page is
    formatted as a right page. It\'s the page placed on the right side
    of the spine of the book or the front side of the page in duplex
    printing.

[`recto`](#recto) [Experimental]

:   If pages progress left-to-right, then this acts like `right`. If
    pages progress right-to-left, then this acts like `left`.

[`verso`](#verso) [Experimental]

:   If pages progress left-to-right, then this acts like `left`. If
    pages progress right-to-left, then this acts like `right`.

Page break aliases
------------------

The `page-break-after` property is now a legacy property, replaced by
[`break-after`](break-after.md).

For compatibility reasons, `page-break-after` should be treated by
browsers as an alias of `break-after`. This ensures that sites using
`page-break-after` continue to work as designed. A subset of values
should be aliased as follows:

  page-break-after   break-after
  ------------------ -------------
  `auto`             `auto`
  `left`             `left`
  `right`            `right`
  `avoid`            `avoid`
  `always`           `page`

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         block-level elements in the normal flow of the root element. User agents may also apply it to other elements like `table-row` elements.
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
page-break-after = 
  auto     |
  always   |
  avoid    |
  left     |
  right    |
  inherit  
```

Examples
--------

### Setting a page break after footnotes

[css]

```css
/* move to a new page after footnotes */
div.footnotes {
  page-break-after: always;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\# page]](https://drafts.csswg.org/css-logical/#page)

[CSS Paged Media Module Level 3\
  [\#
  page-break-after]](https://drafts.csswg.org/css-page/#page-break-after)
  ---------------------------------------------------------------------------------

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

`page-break-after`

1

12

1The values `avoid`, `left`, and `right` are unsupported.

4

7

1.2

37

18

4The values `avoid`, `left`, and `right` are unsupported.

14

1

1.0

See also
--------

- [`break-before`](break-before.md), [`break-after`](break-after.md),
    [`break-inside`](break-inside.md)
- [`page-break-before`](page-break-before.md),
    [`page-break-inside`](page-break-inside.md)
- [`orphans`](orphans.md), [`widows`](widows.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/page-break-after>

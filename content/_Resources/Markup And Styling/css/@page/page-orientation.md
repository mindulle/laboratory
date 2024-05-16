page-orientation
================

The `page-orientation`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) descriptor for
the [`@page`](@page.md) at-rule controls the rotation of a printed page.
It handles the flow of content across pages when the orientation of a
page is changed. This behavior differs from the [`size`](size.md)
descriptor in that a user can define the direction in which to rotate
the page.

This descriptor helps with the layout and orientation of printed
documents, especially when documents are printed double-sided. A user
can specify how the pages will be rotated when printed. This is
particularly useful to lay out content such as tables, which may be
wider than the rest of the content, in a different orientation.

**Note:** [Margin boxes](@page.md#margin_at-rules) and other positional
elements have no special interaction with this descriptor. Margins are
laid out as normal in the unrotated page, then rotated along with
everything else.

Syntax
------

[css]

```css
/* Displays the print content in an upright position */
@page {
  page-orientation: upright;
}

/* Displays the print content rotated counter-clockwise */
@page {
  page-orientation: rotate-left;
}

/* Displays the print content rotated counter-clockwise */
@page {
  page-orientation: rotate-right;
}
```

Values
------

[`upright`](#upright)

:   No orientation is applied and the page is laid out and formatted as
    normal.

[`rotate-left`](#rotate-left)

:   After a page is laid out, the page must be displayed rotated a
    quarter turn to the left (counter-clockwise).

[`rotate-right`](#rotate-right)

:   After the page is laid out, the page must be displayed rotated a
    quarter turn to the right (clockwise).

Formal definition
-----------------

  ------------------------------------- ---------------------
  Related [at-rule](at-rule.md)         [`@page`](@page.md)
  [Initial value](initial_value.md)     `upright`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------

Formal syntax
-------------

```
page-orientation = 
  upright       |
  rotate-left   |
  rotate-right  
```

Examples
--------

### Rotating printed pages

This example shows how the contents of a print document can be rotated
to suit the page content and the page position.

#### CSS

In this first part of the CSS code, [named pages](@page.md#named_pages)
are set up to define the direction in which to rotate the content.

[css]

```css
@page upright {
  size: portrait;
  page-orientation: upright;
}

@page left {
  size: landscape;
  page-orientation: rotate-left;
}

@page right {
  size: landscape;
  page-orientation: rotate-right;
}
```

The following second part of the CSS code declares a named page rule
defined above for the selectors, such as
`<section class="left">…</section>`.

[css]

```css
@media print {
  .upright {
    page: upright;
  }
  .left {
    page: left;
  }
  .right {
    page: right;
  }
}
```

### Result

Click the print button to see the pages rotated.

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Paged Media Module Level 3\
  [\#
  page-orientation-prop]](https://drafts.csswg.org/css-page/#page-orientation-prop)

  -------------------------------------------------------------------------------------------

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

`page-orientation`

85

85

preview

No

71

No

85

85

No

60

No

14.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@page/page-orientation>

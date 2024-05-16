:right
======

The `:right` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md), used with the [`@page`](@page.md)
[at-rule](at-rule.md), represents all right-hand pages of a printed
document.

[css]

```css
/* Selects any right-hand pages when printing */
@page :right {
  margin: 2in 3in;
}
```

Whether a given page is \"left\" or \"right\" is determined by the major
writing direction of the document. For example, if the first page has a
major writing direction of left-to-right then it will be a `:right`
page; if it has a major writing direction of right-to-left then it will
be a [`:left`](:left) page.

**Note:** This pseudo-class can be used to change only the
[`margin`](margin.md), [`padding`](padding.md), [`border`](border.md), and
[`background`](background.md) properties of the *page box*. All other
properties will be ignored, and only the page box, not the document
content on the page, will be affected.

Syntax
------

[css]

```css
:right {
  /* ... */
}
```

Examples
--------

### Setting margins for right-hand pages

[css]

```css
@page :right {
  margin: 2in 3in;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Paged Media Module Level 3\
  [\#
  left-right-first]](https://drafts.csswg.org/css-page/#left-right-first)

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

`:right`

6

12

No

8

9.2

5

≤37

18

No

10.1

4.2

1.0

See also
--------

- [`@page`](@page.md)
- Other page-related pseudo-classes: [`:first`](:first),
    [`:left`](:left)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:right>

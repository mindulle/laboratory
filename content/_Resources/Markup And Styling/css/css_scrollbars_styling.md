CSS scrollbars styling
======================

The **CSS scrollbars styling** module defines properties that you can
use for visual styling of scrollbars. You can customize the width of the
scrollbar as required. You can also customize the color of the scrollbar
*track*, which is the background of the scrollbar, and the color of the
scrollbar *thumb*, which is the draggable handle of the scrollbar.

Scrollbar styling in action
---------------------------

This example defines a thin scrollbar with a red thumb and an orange
track. To view the thumb, you will need to scroll the text. After the
scrollbar is visible, hover over it to see the track.

[css]

```css
.poem {
  overflow: scroll;
  scrollbar-color: red orange;
  scrollbar-width: thin;
}
```

**Note:** When customizing scrollbars, ensure that the thumb and track
have enough contrast with the surrounding background. Also ensure that
the scrollbar hit area is large enough for people who use touch input.

Reference
---------

### CSS properties

- [`scrollbar-width`](scrollbar-width.md)
- [`scrollbar-color`](scrollbar-color.md)

Related concepts
----------------

- [`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md) CSS property
- [`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md) CSS property
- [`overflow-x`](overflow-x.md) CSS property
- [`overflow-y`](overflow-y.md) CSS property
- [`overflow`](overflow.md) CSS shorthand property
- [`overflow-clip-margin`](overflow-clip-margin.md) CSS property
- [`scrollbar-gutter`](scrollbar-gutter.md) CSS property
- [`scroll-behavior`](scroll-behavior.md) CSS property
- [`scroll-margin`](scroll-margin.md) CSS shorthand property
- [`scroll-padding`](scroll-padding.md) CSS shorthand property
- [`scroll-snap-align`](scroll-snap-align.md) CSS property
- [`scroll-snap-stop`](scroll-snap-stop.md) CSS property
- [`scroll-snap-type`](scroll-snap-type.md) CSS property
- [`::-webkit-scrollbar`](::-webkit-scrollbar) pseudo-element
- [scroll
    container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container)
    glossary term
- [`scrollbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/scrollbar_role)
    ARIA role

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Scrollbars Styling Module Level 1\
  ](https://drafts.csswg.org/css-scrollbars/)

  -----------------------------------------------------------------------

See also
--------

- [`scroll-timeline`](scroll-timeline.md),
    [`scroll-timeline-axis`](scroll-timeline-axis.md),
    [`scroll-timeline-name`](scroll-timeline-name.md)
- [CSS overflow](css_overflow.md) module
- [CSS scroll snap](css_scroll_snap.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scrollbars_styling>

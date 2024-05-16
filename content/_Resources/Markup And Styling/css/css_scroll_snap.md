CSS scroll snap
===============

The **CSS scroll snap** module provides properties that let you control
the panning and scrolling behavior by defining snap positions. Content
can be snapped into position as the user scrolls overflowing content
within a [scroll
container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container),
providing paging and scroll positioning.

This module includes the scroll container scroll-padding properties to
adjust the optimal viewing region of paging during scroll-into-view
operations. It also includes scroll-margin and scroll-alignment, set on
the scroll container\'s children, to adjust the children\'s visual area
when that child is scrolled into view, as well as a property to force
scrolling to stop on individual children.

Scroll snap in action
---------------------

To view scroll snapping in the box below, scroll up-and-down and
left-and-right through the grid of 45 numbered boxes in the scrollable
viewport.

With scroll snap, one of the numbered boxes that you scroll to will snap
into place. The initial CSS makes the numbered box snap into the center
of the viewport. Use the sliders to change the block and inline snap
positions.

Using snap properties, you can allow or block the scrolling past an
element, a numbered box in this case. Select the \"Prevent scrolling
past boxes\" checkbox to force all scrolling actions to be limited to
scrolling to an adjacent box.

To compare scroll snapping to regular scrolling, check the \"disable
snapping\" checkbox and try scrolling again.

To see the code for this example, [view the source on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/scroll_snap.html).

Reference
---------

### Properties on containers

- [`scroll-snap-type`](scroll-snap-type.md)
- [`scroll-padding`](scroll-padding.md)
  - [`scroll-padding-top`](scroll-padding-top.md)
  - [`scroll-padding-right`](scroll-padding-right.md)
  - [`scroll-padding-bottom`](scroll-padding-bottom.md)
  - [`scroll-padding-left`](scroll-padding-left.md)
  - [`scroll-padding-inline`](scroll-padding-inline.md)
  - [`scroll-padding-inline-start`](scroll-padding-inline-start.md)
  - [`scroll-padding-inline-end`](scroll-padding-inline-end.md)
  - [`scroll-padding-block`](scroll-padding-block.md)
  - [`scroll-padding-block-start`](scroll-padding-block-start.md)
  - [`scroll-padding-block-end`](scroll-padding-block-end.md)

### Properties on children

- [`scroll-snap-align`](scroll-snap-align.md)
- [`scroll-margin`](scroll-margin.md)
  - [`scroll-margin-top`](scroll-margin-top.md)
  - [`scroll-margin-right`](scroll-margin-right.md)
  - [`scroll-margin-bottom`](scroll-margin-bottom.md)
  - [`scroll-margin-left`](scroll-margin-left.md)
  - [`scroll-margin-inline`](scroll-margin-inline.md)
  - [`scroll-margin-inline-start`](scroll-margin-inline-start.md)
  - [`scroll-margin-inline-end`](scroll-margin-inline-end.md)
  - [`scroll-margin-block`](scroll-margin-block.md)
  - [`scroll-margin-block-start`](scroll-margin-block-start.md)
  - [`scroll-margin-block-end`](scroll-margin-block-end.md)
- [`scroll-snap-stop`](scroll-snap-stop.md)

Guides
------

[Basic concepts of CSS scroll snap](_Resources/Markup%20And%20Styling/css/css_scroll_snap/basic_concepts.md)

:   An overview and examples of CSS scroll snap features.

Related concepts
----------------

- [`:target`](:target) pseudo-class
- [`overflow`](overflow.md) CSS property
- Element
    [`scroll()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll)
    method
- Element
    [`scrollBy()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollBy)
    method
- Element
    [`scrollIntoView()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView)
    method
- Element
    [`scrollTo()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTo)
    method
- Document
    [`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event)
    event
- [`scrollbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/scrollbar_role)
    ARIA role
- [Scroll
    container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container)
    glossary term

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  ](https://drafts.csswg.org/css-scroll-snap/)

  -----------------------------------------------------------------------

See also
--------

- [CSS overflow](css_overflow.md) module
- [CSS scrollbars styling](css_scrollbars_styling.md) module
- [Keyboard-only scrolling
    areas](https://adrianroselli.com/2022/06/keyboard-only-scrolling-areas.html)
    on adrianroselli.com (2022)
- [Scroll snap examples](https://codepen.io/collection/KpqBGW) on
    Codepen (2022)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/) on web.dev (2021)
- [Practical CSS scroll
    snapping/](https://css-tricks.com/practical-css-scroll-snapping/) on
    CSS-Tricks (2020)
- [CSS scroll snap](https://12daysofweb.dev/2022/css-scroll-snap/) on
    12 Days of Web (2019)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll_snap>

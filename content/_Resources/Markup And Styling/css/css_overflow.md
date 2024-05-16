CSS overflow
============

The **CSS overflow** module properties enable you to handle scrollable
overflow in visual media.

Overflow happens when the content in an element box extends past one or
more of the box\'s edges. **Scrollable overflow** is the content that
appears outside the element box for which you might want to add a
scrolling mechanism. CSS overflow properties enable you to control what
happens when content overflows an element box.

Painting effects that overflow the content but do not participate in the
CSS box model do not affect layout. This type of overflow is also known
as [ink
overflow](https://developer.mozilla.org/en-US/docs/Glossary/Ink_overflow).
Examples of ink overflows include box shadows, border images, text
decoration, overhanging glyphs, and outlines. Ink overflows do not
extend the scrollable overflow region.

Overflow in action
------------------

Use the following interactive example to see the effects of various
`overflow` property values on the content overflow and scrollbars in the
adjacent fixed-size box.

The example also includes options to change the values for the
`overflow-clip-margin` and `width` properties, as well as to
programmatically scroll the content if the overflow property creates a
[scroll
container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container).
Select `overflow: clip` and see the effect of different
`overflow-clip-margin` values. Select `overflow: hidden` or
`overflow: scroll` to check out different `ScrollLeft` and `ScrollTop`
slider settings.

A link is included in content box above to demonstrate the effects of
keyboard focus on overflow and scroll behaviors. Try tabbing to the link
or programmatically scrolling the content: the content will scroll only
if the enumerated `<overflow>` value created a scroll container.

Reference
---------

### CSS properties

- [`overflow`](overflow.md) shorthand
- [`overflow-block`](_Resources/Markup%20And%20Styling/css/overflow-block.md)
- [`overflow-clip-margin`](overflow-clip-margin.md)
- [`overflow-inline`](_Resources/Markup%20And%20Styling/css/overflow-inline.md)
- [`overflow-x`](overflow-x.md)
- [`overflow-y`](overflow-y.md)
- [`scroll-behavior`](scroll-behavior.md)
- [`scrollbar-gutter`](scrollbar-gutter.md)
- [`text-overflow`](text-overflow.md)
- [`block-ellipsis`]
- [`continue`]
- [`line-clamp`]
- [`max-lines`]
- [`-webkit-line-clamp`](-webkit-line-clamp.md)
    [Non-standard]

### Data types

- [`<overflow>`](overflow_value.md) enumerated values

Guides
------

[Overflowing content](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Overflowing_content)

:   CSS building block: learn what overflow is and how to manage it.

[[Experimental]](#experimental) [Creating a named scroll timeline](scroll-timeline-name.md#creating_a_named_scroll_timeline)

:   The CSS scroll timeline
    [`scroll-timeline-name`](scroll-timeline-name.md) and
    [`scroll-timeline-axis`](scroll-timeline-axis.md) properties, along
    with the [`scroll-timeline`](scroll-timeline.md) shorthand, create
    animations tied to the scroll offset of a scroll container.

Related concepts
----------------

- [`scrollbar-width`](scrollbar-width.md) CSS property
- [`scrollbar-color`](scrollbar-color.md) CSS property
- [`scrollbar-gutter`](scrollbar-gutter.md) CSS property
- [`scroll-behavior`](scroll-behavior.md) CSS property
- [`scroll-margin`](scroll-margin.md) CSS shorthand property
- [`scroll-padding`](scroll-padding.md) CSS shorthand property
- [`scroll-snap-align`](scroll-snap-align.md) CSS property
- [`scroll-snap-stop`](scroll-snap-stop.md) CSS property
- [`scroll-snap-type`](scroll-snap-type.md) CSS property
- [`text-overflow`](text-overflow.md) CSS property
- [`::-webkit-scrollbar`](::-webkit-scrollbar) pseudo-element
- [`scrollbar`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/scrollbar_role)
    ARIA role
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
- Element
    [`scrollTop`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollTop)
    property
- Element
    [`scrollLeft`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft)
    property
- Element
    [`scrollWidth`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollWidth)
    property
- Element
    [`scrollHeight`](https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollHeight)
    property
- Document
    [`scroll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event)
    event
- [Scroll
    container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container)
    glossary term
- [Ink
    overflow](https://developer.mozilla.org/en-US/docs/Glossary/Ink_overflow)
    glossary term

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Overflow Module Level 3\
  [\#
  propdef-overflow]](https://drafts.csswg.org/css-overflow/#propdef-overflow)

  -------------------------------------------------------------------------------------

See also
--------

- [CSS scrollbars styling](css_scrollbars_styling.md) module
- [CSS scroll snap](css_scroll_snap.md) module
- [CSSOM view](cssom_view.md) module
- How to [debug scrollable
    overflow](https://firefox-source-docs.mozilla.org/devtools-user/page_inspector/how_to/debug_scrollable_overflow/index.html)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_overflow>

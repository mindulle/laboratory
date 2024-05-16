CSS scroll-driven animations
============================

The **CSS scroll-driven animations** module provides functionality that
builds on top of the [CSS animations module](css_animations.md) and [Web
Animations
API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API).
It allows you to animate property values based on a progression along a
scroll-based timeline instead of the default time-based document
timeline. This means that you can animate an element by scrolling a
scrollable element, rather than just by the passing of time.

There are two types of scroll-based timelines:

- *scroll progress timeline*: You progress this timeline by scrolling
    a scrollable element (*scroller*) from top to bottom (or left to
    right) and back again. The position in the scroll range is converted
    into a percentage of progress --- 0% at the start and 100% at the
    end.
- *view progress timeline*: You progress this timeline based on the
    change in visibility of an element (known as the *subject*) inside a
    scroller. The visibility of the subject inside the scroller is
    tracked as a percentage of progress --- by default, the timeline is
    at 0% when the subject is first visible at one edge of the scroller,
    and 100% when it reaches the opposite edge.

When one of these two timelines is applied to an animated element, the
animation progresses along that timeline instead of following the
default time-based timeline.

It is possible to adjust the effective placement of the animation along
the scroll progress and view progress timelines, i.e., you can define
the position at which the animation starts and ends. This can be done in
a couple of different ways:

- Start and end animation range values can be applied to the animation
    to adjust the position of the animation\'s starting and ending
    position along the timeline.
- View progress timelines can have a start and/or end inset (or
    outset) applied to them to adjust the position of the scrollport
    (see [Scroll
    container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container)
    for more details) in which the subject element is deemed to be
    visible. Put another way, this allows you to specify start and/or
    end inset (or outset) values that offset the position of the
    timeline itself.

Scroll-driven animations in action
----------------------------------

You can find several tools and demos showing scroll-driven animations in
action at [Scroll-driven Animations tools and
demos](https://scroll-driven-animations.style/).

Reference
---------

### Properties

Set the timeline that will control the progress of an animation, and set
its attachment range along that timeline:

- [`animation-timeline`](animation-timeline.md)
- [`animation-range`](animation-range.md)
- [`animation-range-start`](animation-range-start.md)
- [`animation-range-end`](animation-range-end.md)

Define *named scroll progress timelines*:

- [`scroll-timeline`](scroll-timeline.md)
- [`scroll-timeline-axis`](scroll-timeline-axis.md)
- [`scroll-timeline-name`](scroll-timeline-name.md)

Define *named view progress timelines*:

- [`view-timeline`](view-timeline.md)
- [`view-timeline-axis`](view-timeline-axis.md)
- [`view-timeline-inset`](view-timeline-inset.md)
- [`view-timeline-name`](view-timeline-name.md)

Modify timeline scope:

- [`timeline-scope`](timeline-scope.md)

### At-rules

CSS scroll-driven animations adds the ability to include
`<timeline-range-name>`s in [`@keyframes`](@keyframes.md) blocks, to place
keyframes at specific positions inside named timeline ranges.

### Functions

Possible values of the [`animation-timeline`](animation-timeline.md)
property for defining *anonymous scroll progress timelines* and
*anonymous view progress timelines* (i.e. implicitly defined by the
browser rather than being explicitly named and defined using the
`scroll-timeline-*` and `view-timeline-*` properties):

- [`scroll()`](scroll.md)
- [`view()`](view.md)

### JavaScript features

- [`Element.animate()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animate)
- [`AnimationTimeline`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationTimeline)
- [`ScrollTimeline`](https://developer.mozilla.org/en-US/docs/Web/API/ScrollTimeline)
- [`ViewTimeline`](https://developer.mozilla.org/en-US/docs/Web/API/ViewTimeline)

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Scroll-driven Animations\
  ](https://drafts.csswg.org/scroll-animations-1/)

  [CSS Animations Level 2\
  ](https://drafts.csswg.org/css-animations-2/)

[Web Animations Level 2\
  ](https://drafts.csswg.org/web-animations-2/)
  -----------------------------------------------------------------------

See also
--------

- [Animate elements on scroll with Scroll-driven
    animations](https://developer.chrome.com/articles/scroll-driven-animations/)
    on developer.chrome.com
- [CSS animations](css_animations.md)
- [Web Animations
    API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scroll-driven_animations>

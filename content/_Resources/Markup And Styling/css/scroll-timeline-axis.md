scroll-timeline-axis
====================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `scroll-timeline-axis`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is used
to specify the scrollbar direction that will be used to provide the
timeline for a *named scroll progress timeline* animation, which is
progressed through by scrolling a scrollable element (*scroller*)
between top and bottom (or left and right). `scroll-timeline` is set on
the scroller that will provide the timeline. See [](css_scroll-driven_animations.md) for more details.

**Note:** If the scroller element does not overflow its container in the
axis dimension or if the overflow is hidden or clipped, no scroll
progress timeline will be created.

The `scroll-timeline-axis` and
[`scroll-timeline-name`](scroll-timeline-name.md) properties can also be
set using the [`scroll-timeline`](scroll-timeline.md) shorthand property.

Syntax
------

[css]

```css
/* Logical property values */
scroll-timeline-axis: block;
scroll-timeline-axis: inline;
/* Non-logical property values */
scroll-timeline-axis: y;
scroll-timeline-axis: x;
```

### Values

Allowed values for `scroll-timeline-axis` are:

[`block`](#block)

:   The scrollbar on the block axis of the scroller element, which is
    the axis in the direction perpendicular to the flow of text within a
    line. For horizontal writing modes, such as standard English, this
    is the same as `y`, while for vertical writing modes, it is the same
    as `x`. This is the default value.

[`inline`](#inline)

:   The scrollbar on the inline axis of the scroller element, which is
    the axis in the direction parallel to the flow of text in a line.
    For horizontal writing modes, this is the same as `x`, while for
    vertical writing modes, this is the same as `y`.

[`y`](#y)

:   The scrollbar on the vertical axis of the scroller element.

[`x`](#x)

:   The scrollbar on the horizontal axis of the scroller element.

Formal definition
-----------------

  ---------------------------------- -------------------
  [Initial value](initial_value.md)     `block`
  Applies to                         scroll containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- -------------------

Formal syntax
-------------

```
scroll-timeline-axis = 
  block       |
  inline      |
  vertical    |
  horizontal  
```

Examples
--------

### Defining the axis of the scroll progress timeline

In this example, a scroll progress timeline named `--myScroller` is
defined using the `scroll-timeline-name` property on the `:root` element
([`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)).
This timeline is then applied to the animation on the element with the
`animation` class using `animation-timeline: --myScroller`.

To demonstrate the effect of `scroll-timeline-axis`, a horizontal
(non-default) scrollbar is used in this example to drive the animation.

#### HTML

The HTML for the example is shown below.

[html]

```html
<body>
  <div class="content"></div>
  <div class="box animation"></div>
</body>
```

#### CSS

The CSS for the container sets the `:root` as the source of a scroll
progress timeline named `--myScroller` using the `scroll-timeline-name`
property. The scroll axis is set using `scroll-timeline-axis: x;`
(Chromium) and `scroll-timeline-axis: horizontal;` (Firefox) --- this
causes the *horizontal scrollbar* position to determine the animation
timeline.

The width of the `.content` element is set to a large value to make it
overflow the `:root` element.

Also worth noting is that the `.animation` element has the timeline
applied to it using `animation-timeline: --myScroller;`, and it also has
an `animation-duration` applied to it so that the example will work in
Firefox.

[css]

```css
:root {
  scroll-timeline-name: --myScroller;

  /* Chromium supports the new x/y syntax */
  scroll-timeline-axis: x;
  /* Firefox still supports the old horizontal/vertical syntax */
  scroll-timeline-axis: horizontal;
}

body {
  margin: 0;
  overflow-y: hidden;
}

.content {
  height: 100vh;
  width: 2000px;
}

.box {
  width: 100px;
  height: 100px;
  border-radius: 10px;
  background-color: rebeccapurple;
  position: fixed;
  top: 25px;
  left: 25px;
}

.animation {
  animation: rotate-appear;
  animation-timeline: --myScroller;
  animation-duration: 1ms; /* Firefox requires this to apply the animation */
}

@keyframes rotate-appear {
  from {
    rotate: 0deg;
    top: 0%;
  }

  to {
    rotate: 720deg;
    top: 100%;
  }
}
```

#### Result

Scroll the horizontal bar at the bottom to see the square animate as you
scroll.

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------

  [Scroll-driven Animations\
  [\#
  propdef-scroll-timeline-axis]](https://drafts.csswg.org/scroll-animations/#propdef-scroll-timeline-axis)

  ------------------------------------------------------------------------------------------------------------------

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

`scroll-timeline-axis`

115

115

111\[\"The syntax of the shorthand property uses the fixed order of name
and then the axis.\", \"Supports the deprecated `horizontal` and
`vertical` values, and not the `x` and `y` values.\", \"The
\`\@scroll-timeline\` at-rule is replaced with the longhand properties
\`scroll-timeline-name\` and \`scroll-timeline-axis\` and the shorthand
property \`scroll-timeline\`.\"\]

No

101

No

115

115

No

No

No

No

See also
--------

- [`animation-timeline`](animation-timeline.md)
- [`scroll-timeline`](scroll-timeline.md),
    [`scroll-timeline-name`](scroll-timeline-name.md)
- [`timeline-scope`](timeline-scope.md)
- [CSS scroll-driven animations](css_scroll-driven_animations.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-axis>

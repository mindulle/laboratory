scroll-timeline-name
====================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `scroll-timeline-name`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is used
to define the name of a *named scroll progress timeline*, which is
progressed through by scrolling a scrollable element (*scroller*)
between top and bottom (or left and right). `scroll-timeline-name` is
set on the scroller that will provide the timeline.

The name is then referenced in an
[`animation-timeline`](animation-timeline.md) declaration to indicate the
container\'s element that is used to drive the progress of the animation
through the scrolling action.

**Note:** If the element does not overflow its container in the axis
dimension or if the overflow is hidden or clipped, no timeline will be
created.

The [`scroll-timeline-axis`](scroll-timeline-axis.md) and
`scroll-timeline-name` properties can also be set using the
[`scroll-timeline`](scroll-timeline.md) shorthand property.

Syntax
------

[css]

```css
scroll-timeline-name: none;
scroll-timeline-name: --custom_name_for_timeline;
```

### Values

Allowed values for `scroll-timeline-name` are:

[`none`](#none)

:   The timeline has no name.

[`<dashed-ident>`](#dashed-ident)

:   An arbitrary custom identifier defining a name for a scroll progress
    timeline, which can then be referenced in an
    [`animation-timeline`](animation-timeline.md) property.

    **Note:** [`<dashed-ident>`](dashed-ident) values must start with
    `--`, which helps avoid name clashes with standard CSS keywords.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         scroll containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   `none` or an ordered list of identifiers
  Animation type                     Not animatable
  ---------------------------------- ------------------------------------------

Formal syntax
-------------

```
scroll-timeline-name = 
  none            |
  <custom-ident>  
```

Examples
--------

### Creating a named scroll progress timeline animation

In this example, a scroll timeline named `--squareTimeline` is defined
using the `scroll-timeline-name` property on the element with the ID
`container`. This is then applied to the animation on the `#square`
element using `animation-timeline: --squareTimeline`.

#### HTML

The HTML for the example is shown below.

[html]

```html
<div id="container">
  <div id="square"></div>
  <div id="stretcher"></div>
</div>
```

#### CSS

The CSS for the container sets it as the source of a scroll timeline
named `--squareTimeline` using the `scroll-timeline-name` property. No
[scrollbar axis](scroll-timeline-axis.md) is defined here because the
vertical axis will be used by default.

The height of the container is set to `300px`, and the container is also
set to create a vertical scrollbar if it overflows (the CSS `height`
rule on the `stretcher` element below does make the content overflow its
container).

[css]

```css
#container {
  height: 300px;
  overflow-y: scroll;
  scroll-timeline-name: --squareTimeline;
  position: relative;
}
```

The CSS below defines a square that rotates according to the timeline
provided by the `animation-timeline` property, which is set to the
`--squareTimeline` timeline named above.

[css]

```css
#square {
  background-color: deeppink;
  width: 100px;
  height: 100px;
  margin-top: 100px;
  animation-name: rotateAnimation;
  animation-duration: 1ms; /* Firefox requires this to apply the animation */
  animation-timeline: --squareTimeline;
  position: absolute;
  bottom: 0;
}

#stretcher {
  height: 600px;
  background: #dedede;
}

@keyframes rotateAnimation {
  from {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(360deg);
  }
}
```

The `stretcher` CSS rule sets the block height to `600px`, which creates
content that overflows the container element, thereby creating scroll
bars. Without this element, the content would not overflow the
container, there would be no scrollbar, and hence no scroll timeline to
associate with the animation timeline.

#### Result

Scroll the vertical bar to see the square animate as you scroll.

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [Scroll-driven Animations\
  [\#
  scroll-timeline-name]](https://drafts.csswg.org/scroll-animations/#scroll-timeline-name)

  --------------------------------------------------------------------------------------------------

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

`scroll-timeline-name`

115

115

111\[\"The syntax of the shorthand property uses the fixed order of name
and then the axis.\", \"The \`\@scroll-timeline\` at-rule is replaced
with the longhand properties \`scroll-timeline-name\` and
\`scroll-timeline-axis\` and the shorthand property
\`scroll-timeline\`.\"\]

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
    [`scroll-timeline-axis`](scroll-timeline-axis.md)
- [`timeline-scope`](timeline-scope.md)
- [CSS scroll-driven animations](css_scroll-driven_animations.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-timeline-name>

animation-range-end
===================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `animation-range-end`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is used
to set the end of an animation\'s attachment range along its timeline,
i.e. where along the timeline an animation will end.

The `animation-range-end` and
[`animation-range-start`](animation-range-start.md) properties can also be
set using the [`animation-range`](animation-range.md) shorthand property.

**Note:** [`animation-range-end`](animation-range-end.md) is included in
the [`animation`](animation.md) shorthand as a reset-only value. This means
that including `animation` resets a previously-declared
`animation-range-end` value to `normal`, but a specific value cannot be
set via `animation`. When creating [](css_scroll-driven_animations.md), you need to declare
`animation-range-end` after declaring any `animation` shorthand for it
to take effect.

Syntax
------

[css]

```css
/* Keyword or length percentage value */
animation-range-end: normal;
animation-range-end: 80%;
animation-range-end: 700px;

/* Named timeline range value */
animation-range-end: cover;
animation-range-end: contain;
animation-range-end: cover 80%;
animation-range-end: contain 700px;
```

### Values

Allowed values for `animation-range-end` are `normal`, a
[`<length-percentage>`](length-percentage.md), a `<timeline-range-name>`,
or a `<timeline-range-name>` with a `<length-percentage>` following it.
See [`animation-range`](animation-range.md) for a detailed description of
the available values.

Also check out the [View Timeline Ranges
Visualizer](https://scroll-driven-animations.style/tools/view-timeline/ranges/),
which shows exactly what the different values mean in an easy visual
format.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  Percentages                        Relative to the specified named timeline range if specified, otherwise relative to the entire timeline
  [Computed value](computed_value.md)   A list where each item may be \'normal\', a length percentage, or a timeline range name and a length percentage
  Animation type                     Not animatable
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

Error: could not find syntax for this item

Examples
--------

### Creating a named view progress timeline with range end

A view progress timeline named `--subjectReveal` is defined using the
`view-timeline` property on a subject element with a `class` of
`animation`. This is then set as the timeline for the same element using
`animation-timeline: --subjectReveal;`. The result is that the subject
element animates as it moves upwards through the document as it is
scrolled.

An `animation-range-end` declaration is also set to make the animation
end earlier than expected.

#### HTML

The HTML for the example is shown below.

[html]

```html
<div class="content">
  <h1>Content</h1>

  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Risus quis varius quam
    quisque id. Et ligula ullamcorper malesuada proin libero nunc consequat
    interdum varius. Elit ullamcorper dignissim cras tincidunt lobortis feugiat
    vivamus at augue.
  </p>

  <p>
    Dolor sed viverra ipsum nunc aliquet. Sed sed risus pretium quam vulputate
    dignissim. Tortor aliquam nulla facilisi cras. A erat nam at lectus urna
    duis convallis convallis. Nibh ipsum consequat nisl vel pretium lectus.
    Sagittis aliquam malesuada bibendum arcu vitae elementum. Malesuada bibendum
    arcu vitae elementum curabitur vitae nunc sed velit.
  </p>

  <div class="subject animation"></div>

  <p>
    Adipiscing enim eu turpis egestas pretium aenean pharetra magna ac. Arcu
    cursus vitae congue mauris rhoncus aenean vel. Sit amet cursus sit amet
    dictum. Augue neque gravida in fermentum et. Gravida rutrum quisque non
    tellus orci ac auctor augue mauris. Risus quis varius quam quisque id diam
    vel quam elementum. Nibh praesent tristique magna sit amet purus gravida
    quis. Duis ultricies lacus sed turpis tincidunt id aliquet. In egestas erat
    imperdiet sed euismod nisi. Eget egestas purus viverra accumsan in nisl nisi
    scelerisque. Netus et malesuada fames ac.
  </p>
</div>
```

#### CSS

The `subject` element and its containing `content` element are styled
minimally, and the text content is given some basic font settings:

[css]

```css
.subject {
  width: 300px;
  height: 200px;
  margin: 0 auto;
  background-color: deeppink;
}

.content {
  width: 75%;
  max-width: 800px;
  margin: 0 auto;
}

p,
h1 {
  font-family: Arial, Helvetica, sans-serif;
}

h1 {
  font-size: 3rem;
}

p {
  font-size: 1.5rem;
  line-height: 1.5;
}
```

The `<div>` with the class of `subject` is also given a class of
`animation` --- this is where `view-timeline` is set to define a named
view progress timeline. It is also given an `animation-timeline` name
with the same value to declare that this will be the element animated as
the view progress timeline is progressed. We also give it an
`animation-range-end` declaration to make the animation end earlier than
expected.

Last, an animation is specified on the element that animates its opacity
and scale, causing it to fade in and size up as it moves up the
scroller.

[css]

```css
.animation {
  view-timeline: --subjectReveal block;
  animation-timeline: --subjectReveal;

  animation-name: appear;
  animation-range-end: contain 50%;
  animation-fill-mode: both;
  animation-duration: 1ms; /* Firefox requires this to apply the animation */
}

@keyframes appear {
  from {
    opacity: 0;
    transform: scaleX(0);
  }

  to {
    opacity: 1,
    transform: scaleX(1);
  }
}
```

#### Result

Scroll to see the subject element being animated.

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [Scroll-driven Animations\
  [\#
  animation-range-end]](https://drafts.csswg.org/scroll-animations/#animation-range-end)

  ------------------------------------------------------------------------------------------------

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

`animation-range-end`

115

115

No

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
- [`animation-range`](animation-range.md),
    [`animation-range-start`](animation-range-start.md)
- [`scroll-timeline`](scroll-timeline.md),
    [`scroll-timeline-axis`](scroll-timeline-axis.md),
    [`scroll-timeline-name`](scroll-timeline-name.md)
- [`timeline-scope`](timeline-scope.md)
- [`view-timeline-inset`](view-timeline-inset.md)
- The JavaScript equivalent: The `rangeEnd` property available in
    [`Element.animate()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animate)
    calls
- [CSS scroll-driven animations](css_scroll-driven_animations.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-range-end>

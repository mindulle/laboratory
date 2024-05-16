view-timeline-inset
===================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `view-timeline-inset`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is used
to specify one or two values representing an adjustment to the position
of the scrollport (see [Scroll
container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container)
for more details) in which the subject element of a *named view progress
timeline* animation is deemed to be visible. Put another way, this
allows you to specify start and/or end inset (or outset) values that
offset the position of the timeline.

This can be combined with or used instead of
[`animation-range`](animation-range.md) and its longhand properties, which
can be used to set the attachment range of an animation along its
timeline. See [](css_scroll-driven_animations.md) for more details.

Syntax
------

[css]

```css
/* Single value */
view-timeline-inset: auto;
view-timeline-inset: 200px;
view-timeline-inset: 20%;

/* Two values */
view-timeline-inset: 20% auto;
view-timeline-inset: auto 200px;
view-timeline-inset: 20% 200px;
```

### Values

Allowed values for `view-timeline-inset` are:

[`auto`](#auto)

:   If set, the corresponding [`scroll-padding`](scroll-padding.md) (or
    equivalent longhand value) for that edge of the scrollport is used.
    If this is not set (or set to `auto`), the value will usually be 0,
    although some user agents may use heuristics to determine a
    different default value if appropriate.

[`<length-percentage>`](length-percentage.md)

:   Any valid `<length-percentage>` value is accepted as an inset/outset
    value.

    -   If the value is positive, the position of the animation\'s
        start/end will be moved inside the scrollport by the specified
        length or percentage.
    -   If the value is negative, the position of the animation\'s
        start/end will be moved outside the scrollport by the specified
        length or percentage, i.e. it will start animating before it
        appears in the scrollport, or finish animating after it leaves
        the scrollport.

If two values are provided, the first value represents the start
inset/outset in the relevant axis (where the animation begins) and the
second value represents the end inset/outset (where the animation ends).
If only one value is provided, the start and end inset/outset are both
set to the same value.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  Percentages                        Relative to the corresponding dimension of the relevant scrollport
  [Computed value](computed_value.md)   A list where each item may be either \'auto\' or a length percentage
  Animation type                     by computed value type
  ---------------------------------- ----------------------------------------------------------------------

Formal syntax
-------------

```
view-timeline-inset = 
  [ [ auto | <length-percentage> ] ]#  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Creating a named view progress timeline with inset

A view progress timeline named `--subjectReveal` is defined using the
`view-timeline` property on a subject element with a `class` of
`animation`. This is then set as the timeline for the same element using
`animation-timeline: --subjectReveal;`. The result is that the subject
element animates as it moves upwards through the document as it is
scrolled.

A `view-timeline-inset` declaration is also set to make the animation
begin later than expected, and finish earlier.

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
view progress timeline. We also give it a `view-timeline-inset`
declaration to make the animation begin later than expected, and finish
earlier. It is also given an `animation-timeline` name with the same
value to declare that this will be the element animated as the view
progress timeline is progressed.

Last, an animation is specified on the element that animates its opacity
and scale, causing it to fade in and size up as it moves up the
scroller.

[css]

```css
.animation {
  view-timeline: --subjectReveal block;
  view-timeline-inset: 70% -100px;
  animation-timeline: --subjectReveal;

  animation-name: appear;
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
  view-timeline-inset]](https://drafts.csswg.org/scroll-animations/#view-timeline-inset)

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

`view-timeline-inset`

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
- [`timeline-scope`](timeline-scope.md)
- [`view-timeline`](view-timeline.md),
    [`view-timeline-axis`](view-timeline-axis.md),
    [`view-timeline-name`](view-timeline-name.md)
- [CSS scroll-driven animations](css_scroll-driven_animations.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/view-timeline-inset>

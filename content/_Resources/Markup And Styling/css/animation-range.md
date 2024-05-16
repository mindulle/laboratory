animation-range
===============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `animation-range`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](shorthand_properties.md) is used to set the start and end of an
animation\'s attachment range along its timeline, i.e. where along the
timeline an animation will start and end.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`animation-range-start`](animation-range-start.md)
- [`animation-range-end`](animation-range-end.md)

Syntax
------

[css]

```css
/* single keyword or length percentage value */
animation-range: normal; /* Equivalent to normal normal */
animation-range: 20%; /* Equivalent to 20% normal */
animation-range: 100px; /* Equivalent to 100px normal */

/* single named timeline range value */
animation-range: cover; /* Equivalent to cover 0% cover 100% */
animation-range: contain; /* Equivalent to contain 0% contain 100% */
animation-range: cover 20%; /* Equivalent to cover 20% cover 100% */
animation-range: contain 100px; /* Equivalent to contain 100px cover 100% */

/* two values for range start and end */
animation-range: normal 25%;
animation-range: 25% normal;
animation-range: 25% 50%;
animation-range: entry exit; /* Equivalent to entry 0% exit 100% */
animation-range: cover cover 200px; /* Equivalent to cover 0% cover 200px */
animation-range: entry 10% exit; /* Equivalent to entry 10% exit 100% */
animation-range: 10% exit 90%;
animation-range: entry 10% 90%;
```

The `animation-range` shorthand property can be applied to a container
element as a combination of the `<animation-range-start>` and
`<animation-range-end>` values. If both the values are specified, they
will be interpreted in the order `<animation-range-start>` then
`<animation-range-end>`.

As shown by the comments in the syntax block above, if only a single
value is provided there are a couple of possible interpretations:

- If the value is a [`<length-percentage>`](length-percentage.md) or
    `normal`, `<animation-range-start>` will take that value, and
    `<animation-range-end>` will equal `normal`.
- If the value is a named timeline range without a
    `<length-percentage>` following it, the range will be between that
    named timeline range at 0% and 100%.
- If the value is a named timeline range with a `<length-percentage>`
    following it, the range will start at that named timeline range and
    percentage, and end at that named timeline range and 100%.

### Values

One or two values representing the
[`animation-range-start`](animation-range-start.md) and/or
[`animation-range-end`](animation-range-end.md). These values can be one of
the following:

[`normal`](#normal)

:   Represents the start of the timeline in the case of
    `animation-range-start` and the end of the timeline in the case of
    `animation-range-end`. This is the default value.

[`<length-percentage>`](#length-percentage)

:   A length or percentage value measured from the beginning of the
    timeline.

[`<timeline-range-name>`](#timeline-range-name)

:   A specific named timeline range inside the overall timeline.
    Possible values are:

    [`cover`](#cover)

    :   Represents the full range of a *named view progress timeline*
        (see [CSS scroll-driven
        animations](css_scroll-driven_animations) for more details),
        from the point where the subject element first starts to enter
        the scroll port\'s view progress visibility range (0% progress)
        to the point where it has completely left it (100% progress).

    [`contain`](#contain)

    :   Represents the range of a *named view progress timeline* where
        the subject element is fully contained by, or fully contains,
        the scroll port\'s view progress visibility range.

        -   If the subject element is smaller than the scrollport, it
            ranges from the point where the subject element is first
            completely contained by the scroll port (0% progress), to
            the point where it is no longer completely contained by the
            scroll port (100% progress).
        -   If the subject element is larger than the scrollport, it
            ranges from the point where the subject element first
            completely covers the scroll port (0% progress), to the
            point where it no longer completely covers the scroll port
            (100% progress).

    [`entry`](#entry)

    :   Represents the range of a *named view progress timeline* from
        the point where the subject element first starts to enter the
        scroll port (0% progress), to the point where it has completely
        entered the scroll port (100%).

    [`exit`](#exit)

    :   Represents the range of a *named view progress timeline* from
        the point where the subject element first starts to exit the
        scroll port (0% progress), to the point where it has completely
        exited the scroll port (100%).

    [`entry-crossing`](#entry-crossing)

    :   Represents the range of a *named view progress timeline* from
        the point where the subject element first starts to cross the
        scroll port\'s starting edge (0% progress), to the point where
        it has completely crossed the scroll port\'s starting edge
        (100%).

    [`exit-crossing`](#exit-crossing)

    :   Represents the range of a *named view progress timeline* from
        the point where the subject element first starts to cross the
        scroll port\'s end edge (0% progress), to the point where it has
        completely crossed the scroll port\'s end edge (100%).

    In the case of `<timeline-range-name>` values that do not include a
    `<length-percentage>`, the percentage defaults to `0%` if it is an
    `animation-range-start` value, and `100%` if it is an
    `animation-range-end` value.

    
    **Note:** It is quite hard to visualize what these values mean from
    the descriptions above. Fortunately, the [View Timeline Ranges
    Visualizer](https://scroll-driven-animations.style/tools/view-timeline/ranges/)
    shows exactly what they mean in an easy visual format.

[`<timeline-range-name> <length-percentage>`](#timeline-range-name_length-percentage)

:   A combination value that equals the specified percentage or distance
    through the specified named timeline range, measured from the start
    of that timeline range.

**Note:** The scroll port (see [Scroll
container](https://developer.mozilla.org/en-US/docs/Glossary/Scroll_container)
for more details) area known as the view progress visibility range is
the area inside which the subject element of a *named view progress
timeline* animation is deemed to be visible. By default, this is the
full range of the scrollport, but it can be adjusted using the
[`view-timeline-inset`](view-timeline-inset.md) property.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](animation-range-start.md): |
|                                   |     `normal`                      |
|                                   | -   [](animation-range-end.md): |
|                                   |     `normal`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | Relative to the specified named   |
|                                   | timeline range if specified,      |
|                                   | otherwise relative to the entire  |
|                                   | timeline                          |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](animation-range-start.md): |
|                                   |     A list where each item may be |
|                                   |     \'normal\', a length          |
|                                   |     percentage, or a timeline     |
|                                   |     range name and a length       |
|                                   |     percentage                    |
|                                   | -   [](animation-range-end.md): |
|                                   |     A list where each item may be |
|                                   |     \'normal\', a length          |
|                                   |     percentage, or a timeline     |
|                                   |     range name and a length       |
|                                   |     percentage                    |
+-----------------------------------+-----------------------------------+
| Animation type                    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](animation-range-start.md): |
|                                   |     Not animatable                |
|                                   | -   [](animation-range-end.md): |
|                                   |     Not animatable                |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
animation-range = 
  [ <'animation-delay-start'> <'animation-delay-end'>? | <timeline-range-name> ]#  
```

Examples
--------

### View Timeline Ranges Visualizer

See the [View Timeline Ranges
Visualizer](https://scroll-driven-animations.style/tools/view-timeline/ranges/)
for a nice easy visual explanation of what all the value types mean.

### Creating a named view progress timeline with range

A view progress timeline named `--subjectReveal` is defined using the
`view-timeline` property on a subject element with a `class` of
`animation`. This is then set as the timeline for the same element using
`animation-timeline: --subjectReveal;`. The result is that the subject
element animates as it moves upwards through the document as it is
scrolled.

An `animation-range` declaration is also set to make the animation begin
later than expected, and finish earlier.

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
`animation-range` declaration to make the animation begin later than
expected, and finish earlier.

Last, an animation is specified on the element that animates its opacity
and scale, causing it to fade in and size up as it moves up the
scroller.

[css]

```css
.animation {
  view-timeline: --subjectReveal block;
  animation-timeline: --subjectReveal;

  animation-name: appear;
  animation-range: entry 10% contain 25%;
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

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Scroll-driven Animations\
  [\#
  animation-range]](https://drafts.csswg.org/scroll-animations/#animation-range)

  ----------------------------------------------------------------------------------------

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

`animation-range`

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
- [`animation-range-end`](animation-range-end.md),
    [`animation-range-start`](animation-range-start.md)
- [`scroll-timeline`](scroll-timeline.md),
    [`scroll-timeline-axis`](scroll-timeline-axis.md),
    [`scroll-timeline-name`](scroll-timeline-name.md)
- [`timeline-scope`](timeline-scope.md)
- [`view-timeline-inset`](view-timeline-inset.md)
- [CSS scroll-driven animations](css_scroll-driven_animations.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-range>

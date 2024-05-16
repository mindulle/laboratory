animation-duration
==================

The `animation-duration`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the length of time that an animation takes to complete one cycle.

Try it
------

It is often convenient to use the shorthand property
[`animation`](animation.md) to set all animation properties at once.

Syntax
------

[css]

```css
/* Single animation */
animation-duration: auto; /* Default */
animation-duration: 6s;
animation-duration: 120ms;

/* Multiple animations */
animation-duration: 1.64s, 15.22s;
animation-duration: 10s, 35s, 230ms;

/* Global values */
animation-duration: inherit;
animation-duration: initial;
animation-duration: revert;
animation-duration: revert-layer;
animation-duration: unset;
```

### Values

[`auto`](#auto) [Experimental]

:   For time-based animations, `auto` is equivalent to a value of `0s`
    (see below). For [](css_scroll-driven_animations.md), `auto` fills the entire
    timeline with the animation.

`<time>`

:   The time that an animation takes to complete one cycle. This may be
    specified in either seconds (`s`) or milliseconds (`ms`). The value
    must be positive or zero and the unit is required.

    If no value is provided, the default value of `0s` is used, in which
    case the animation still executes (the
    [`animationStart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationstart_event)
    and
    [`animationEnd`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationend_event)
    events are fired). Whether or not the animation will be visible when
    the duration is `0s` will depend on the value of
    [`animation-fill-mode`](animation-fill-mode), as explained below:

    -   If `animation-fill-mode` is set to `backwards` or `both`, the
        first frame of the animation as defined by `animation-direction`
        will be displayed during [`animation-delay`](animation-delay)
        countdown.
    -   If `animation-fill-mode` is set to `forwards` or `both`, the
        last frame of the animation will be displayed, as defined by
        `animation-direction`, after the `animation-delay` expires.
    -   If `animation-fill-mode` is set to `none`, the animation will
        have no visible effect.

**Note:** Negative values are invalid, causing the declaration to be
ignored. Some early, prefixed, implementations may consider them as
identical to `0s`.

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they are applied to the animations in the order
in which the [`animation-name`](animation-name.md)s appear. For situations
where the number of animations and `animation-*` property values do not
match, see [](using_css_animations.md#setting_multiple_animation_property_values).

**Note:** When creating [](css_scroll-driven_animations.md), specifying an
`animation-duration` value in seconds or milliseconds doesn\'t really
make sense. In tests, it seemed to have no effect on scroll progress
timeline animations, while on view progress timeline animations it
seemed to push the animation to happen nearer the end of the timeline.
However, Firefox requires an `animation-duration` to be set for it to
successfully apply the animation. You are therefore advised to set
`animation-duration` to `1ms` so that animations will work in Firefox,
but the effect is not altered too much by it.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0s`
  Applies to                         all elements, [`::before`](::before) and [`::after`](::after) [pseudo-elements](pseudo-elements.md)
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
animation-duration = 
  <time [0s,∞]>#  
```

Examples
--------

### Setting animation duration

This animation has an animation-duration of 0.7 seconds.

#### HTML

[html]

```html
<div class="box"></div>
```

#### CSS

[css]

```css
.box {
  background-color: rebeccapurple;
  border-radius: 10px;
  width: 100px;
  height: 100px;
}

.box:hover {
  animation-name: rotate;
  animation-duration: 0.7s;
}

@keyframes rotate {
  0% {
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}
```

#### Result

Hover over the rectangle to start the animation.

See [CSS animations](using_css_animations.md) for more
examples.

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation-duration]](https://drafts.csswg.org/css-animations/#animation-duration)

  -------------------------------------------------------------------------------------------

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

`animation-duration`

433

1212

49165

10Once the element has loaded, changing the value of this property has
no effect.

301512.1--1512--15

94

432

4318

49165

301412.1--1412--14

94.2

4.01.0

`auto`

115

115

NoFirefox does not currently support the `auto` value and only accepts
values in seconds or milliseconds. It\'s recommended that *1ms* is used
until `auto` is supported.

No

101

No

115

115

NoFirefox does not currently support the `auto` value and only accepts
values in seconds or milliseconds. It\'s recommended that *1ms* is used
until `auto` is supported.

No

No

No

See also
--------

- [Using CSS animations](using_css_animations.md)
- JavaScript
    [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
    API
- Other related animation properties: [`animation`](animation.md),
    [`animation-composition`](animation-composition.md),
    [`animation-delay`](animation-delay.md),
    [`animation-direction`](animation-direction.md),
    [`animation-fill-mode`](animation-fill-mode.md),
    [`animation-iteration-count`](animation-iteration-count.md),
    [`animation-name`](animation-name.md),
    [`animation-play-state`](animation-play-state.md),
    [`animation-timeline`](animation-timeline.md),
    [`animation-timing-function`](animation-timing-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration>

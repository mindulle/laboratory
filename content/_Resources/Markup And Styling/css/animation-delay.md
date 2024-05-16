animation-delay
===============

The `animation-delay`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the amount of time to wait from applying the animation to an
element before beginning to perform the animation. The animation can
start later, immediately from its beginning, or immediately and partway
through the animation.

Try it
------

It is often convenient to use the shorthand property
[`animation`](animation.md) to set all animation properties at once.

Syntax
------

[css]

```css
/* Single animation */
animation-delay: 3s;
animation-delay: 0s;
animation-delay: -1500ms;

/* Multiple animations */
animation-delay: 2.1s, 480ms;

/* Global values */
animation-delay: inherit;
animation-delay: initial;
animation-delay: revert;
animation-delay: revert-layer;
animation-delay: unset;
```

### Values

`<time>`

:   The time offset, from the moment at which the animation is applied
    to the element, at which the animation should begin. This may be
    specified in either seconds (`s`) or milliseconds (`ms`). The unit
    is required.

    A positive value indicates that the animation should begin after the
    specified amount of time has elapsed. A value of `0s`, which is the
    default, indicates that the animation should begin as soon as it\'s
    applied.

    A negative value causes the animation to begin immediately, but
    partway through its cycle. For example, if you specify `-1s` as the
    animation delay time, the animation will begin immediately but will
    start 1 second into the animation sequence. If you specify a
    negative value for the animation delay, but the starting value is
    implicit, the starting value is taken from the moment the animation
    is applied to the element.

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they are applied to the animations in the order
in which the [`animation-name`](animation-name.md)s appear. For situations
where the number of animations and `animation-*` property values do not
match, see [](using_css_animations.md#setting_multiple_animation_property_values).

**Note:** `animation-delay` has no effect on [](css_scroll-driven_animations.md).

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
animation-delay = 
  [ <'animation-delay-start'> <'animation-delay-end'>? | <timeline-range-name> ]#  
```

Examples
--------

### Setting an animation delay

This animation has a delay of 2 seconds.

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
  animation-delay: 2s;
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

See [CSS animations](using_css_animations.md) for examples.

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation-delay]](https://drafts.csswg.org/css-animations/#animation-delay)

  -------------------------------------------------------------------------------------

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

`animation-delay`

433

1212

49

16Before Firefox 57, Firefox does not repaint elements outside the
viewport that are animated into the viewport with a delay. This bug
affects only some platforms, such as Windows.

5

10

301512.1--1512--15

94

43≤37

4318

49165

301412.1--1412--14

93.2

4.01.0

See also
--------

- [Using CSS animations](using_css_animations.md)
- JavaScript
    [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
    API
- Other related animation properties: [`animation`](animation.md),
    [`animation-composition`](animation-composition.md),
    [`animation-direction`](animation-direction.md),
    [`animation-duration`](animation-duration.md),
    [`animation-fill-mode`](animation-fill-mode.md),
    [`animation-iteration-count`](animation-iteration-count.md),
    [`animation-name`](animation-name.md),
    [`animation-play-state`](animation-play-state.md),
    [`animation-timeline`](animation-timeline.md),
    [`animation-timing-function`](animation-timing-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay>

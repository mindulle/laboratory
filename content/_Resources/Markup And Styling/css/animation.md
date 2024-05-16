animation
=========

The `animation` [shorthand](shorthand_properties.md)
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies
an animation between styles. It is a shorthand for
[`animation-name`](animation-name.md),
[`animation-duration`](animation-duration.md),
[`animation-timing-function`](animation-timing-function.md),
[`animation-delay`](animation-delay.md),
[`animation-iteration-count`](animation-iteration-count.md),
[`animation-direction`](animation-direction.md),
[`animation-fill-mode`](animation-fill-mode.md),
[`animation-play-state`](animation-play-state.md), and
[`animation-timeline`](animation-timeline.md).

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`animation-delay`](animation-delay.md)
- [`animation-direction`](animation-direction.md)
- [`animation-duration`](animation-duration.md)
- [`animation-fill-mode`](animation-fill-mode.md)
- [`animation-iteration-count`](animation-iteration-count.md)
- [`animation-name`](animation-name.md)
- [`animation-play-state`](animation-play-state.md)
- [`animation-timeline`](animation-timeline.md)
- [`animation-timing-function`](animation-timing-function.md)

Syntax
------

[css]

```css
/* @keyframes duration | easing-function | delay |
iteration-count | direction | fill-mode | play-state | name */
animation: 3s ease-in 1s 2 reverse both paused slidein;

/* @keyframes duration | easing-function | delay | name */
animation: 3s linear 1s slidein;

/* two animations */
animation:
  3s linear slidein,
  3s ease-out 5s slideout;
```

The `animation` property is specified as one or more single animations,
separated by commas.

Each individual animation is specified as:

- zero, one, or two occurrences of the [`<time>`](time.md) value
- zero or one occurrences of the following values:
  - [`<single-easing-function>`](animation.md#single-easing-function)
  - [`<single-animation-iteration-count>`](animation.md#single-animation-iteration-count)
  - [`<single-animation-direction>`](animation.md#single-animation-direction)
  - [`<single-animation-fill-mode>`](animation.md#single-animation-fill-mode)
  - [`<single-animation-play-state>`](animation.md#single-animation-play-state)
- an optional name for the animation, which may be `none`, a
    [`<custom-ident>`](custom-ident.md), or a [`<string>`](string.md)

**Note:** [`animation-timeline`](animation-timeline.md),
[`animation-range-start`](animation-range-start.md), and
[`animation-range-end`](animation-range-end.md) are not currently included
in this list, as current implementations are reset-only. This means that
including `animation` resets a previously-declared `animation-timeline`
value to `auto` and previously-declared `animation-range-start` and
`animation-range-end` values to `normal`, but these properties cannot be
set via `animation`. When creating [](css_scroll-driven_animations.md), you need to declare these
properties after declaring any `animation` shorthand for it to take
effect.

### Values

[`<single-easing-function>`](#single-easing-function)

:   Determines the type of transition. The value must be one of those
    available in [`<easing-function>`](easing-function.md).

[`<single-animation-iteration-count>`](#single-animation-iteration-count)

:   The number of times the animation is played. The value must be one
    of those available in
    [`animation-iteration-count`](animation-iteration-count.md).

[`<single-animation-direction>`](#single-animation-direction)

:   The direction in which the animation is played. The value must be
    one of those available in
    [`animation-direction`](animation-direction.md).

[`<single-animation-fill-mode>`](#single-animation-fill-mode)

:   Determines how styles should be applied to the animation\'s target
    before and after its execution. The value must be one of those
    available in [`animation-fill-mode`](animation-fill-mode.md).

[`<single-animation-play-state>`](#single-animation-play-state)

:   Determines whether the animation is playing or not. The value must
    be one of those available in
    [`animation-play-state`](animation-play-state.md).

Description
-----------

The order of time values within each animation definition is important:
the first value that can be parsed as a [`<time>`](time.md) is assigned to
the [`animation-duration`](animation-duration.md), and the second one is
assigned to [`animation-delay`](animation-delay.md).

The order of other values within each animation definition is also
important for distinguishing an [`animation-name`](animation-name.md) value
from other values. If a value in the `animation` shorthand can be parsed
as a value for an animation property other than `animation-name`, then
the value will be applied to that property first and not to
`animation-name`. For this reason, the recommended practice is to
specify a value for `animation-name` as the last value in a list of
values when using the `animation` shorthand; this holds true even when
you specify multiple, comma-separated animations using the `animation`
shorthand.

While an animation name must be set for an animation to be applied, all
values of the `animation` shorthand are optional, and default to the
initial value for each long-hand `animation` component. The initial
value of `animation-name` is `none`, meaning if no `animation-name`
value is declared in the `animation` shorthand property, there is no
animation to apply on any of the properties.

When the `animation-duration` value is omitted from the `animation`
shorthand property, the value for this property defaults to `0s`. In
this case, the animation will still occur (the
[`animationStart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationstart_event)
and
[`animationEnd`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationend_event)
events will be fired) but no animation will be visible.

Accessibility concerns
----------------------

Blinking and flashing animation can be problematic for people with
cognitive concerns such as Attention Deficit Hyperactivity Disorder
(ADHD). Additionally, certain kinds of motion can be a trigger for
Vestibular disorders, epilepsy, and migraine and Scotopic sensitivity.

Consider providing a mechanism for pausing or disabling animation as
well as using the [](prefers-reduced-motion.md) to create a complimentary
experience for users who have expressed a preference for reduced
animated experiences.

- [Designing Safer Web Animation For Motion Sensitivity · An A List
    Apart
    Article](https://alistapart.com/article/designing-safer-web-animation-for-motion-sensitivity/)
- [An Introduction to the Reduced Motion Media Query \|
    CSS-Tricks](https://css-tricks.com/introduction-reduced-motion-media-query/)
- [Responsive Design for Motion \|
    WebKit](https://webkit.org/blog/7551/responsive-design-for-motion/)
- [MDN Understanding WCAG, Guideline 2.2
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.2_%e2%80%94_enough_time_provide_users_enough_time_to_read_and_use_content)
- [Understanding Success Criterion 2.2.2 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-pause.html)

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](animation-name.md): |
|                                   |     `none`                        |
|                                   | -   [](animation-duration.md): |
|                                   |     `0s`                          |
|                                   | -   [](animation-timing-function.md): |
|                                   |     `ease`                        |
|                                   | -   [](animation-delay.md): |
|                                   |     `0s`                          |
|                                   | -   [](animation-iteration-count.md): |
|                                   |     `1`                           |
|                                   | -   [](animation-direction.md): |
|                                   |     `normal`                      |
|                                   | -   [](animation-fill-mode.md): |
|                                   |     `none`                        |
|                                   | -   [](animation-play-state.md): |
|                                   |     `running`                     |
|                                   | -   [](animation-timeline.md): |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](animation-name.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-duration.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-timing-function.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-delay.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-direction.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-iteration-count.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-fill-mode.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-play-state.md): |
|                                   |     as specified                  |
|                                   | -   [](animation-timeline.md): |
|                                   |     a list, each item either a    |
|                                   |     case-sensitive CSS identifier |
|                                   |     or the keywords `none`,       |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Animation type                    | Not animatable                    |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
animation = 
  <single-animation>#  

<single-animation> = 
  <time>                              ||
  <easing-function>                   ||
  <time>                              ||
  <single-animation-iteration-count>  ||
  <single-animation-direction>        ||
  <single-animation-fill-mode>        ||
  <single-animation-play-state>       ||
  [ none | <keyframes-name> ]         

<easing-function> = 
  linear                          |
  <linear-easing-function>        |
  <cubic-bezier-easing-function>  |
  <step-easing-function>          

<single-animation-iteration-count> = 
  infinite        |
  <number [0,∞]>  

<single-animation-direction> = 
  normal             |
  reverse            |
  alternate          |
  alternate-reverse  

<single-animation-fill-mode> = 
  none       |
  forwards   |
  backwards  |
  both       

<single-animation-play-state> = 
  running  |
  paused   

<keyframes-name> = 
  <custom-ident>  |
  <string>        

<linear-easing-function> = 
  linear( <linear-stop-list> )  

<cubic-bezier-easing-function> = 
  ease                                                |
  ease-in                                             |
  ease-out                                            |
  ease-in-out                                         |
  cubic-bezier( <number [0,1]> , <number> , <number [0,1]> , <number> )  

<step-easing-function> = 
  step-start                                |
  step-end                                  |
  steps( <integer> [, <step-position> ]? )  

<linear-stop-list> = 
  [ <linear-stop> ]#  

<step-position> = 
  jump-start  |
  jump-end    |
  jump-none   |
  jump-both   |
  start       |
  end         

<linear-stop> = 
  <number>               &&
  <linear-stop-length>?  

<linear-stop-length> = 
  <percentage>  
```

Examples
--------

**Note:** Animating [CSS Box Model](css_box_model.md) properties is
discouraged. Animating any box model property is inherently CPU
intensive; consider animating the [transform](transform.md) property
instead.

### Sun Rise

Here we animate a yellow sun across a light blue sky. The sun rises to
the center of the viewport and then falls out of sight.

[html]

```html
<div class="sun"></div>
```

[css]

```css
:root {
  overflow: hidden; /* hides any part of the sun below the horizon */
  background-color: lightblue;
  display: flex;
  justify-content: center; /* centers the sun in the background */
}

.sun {
  background-color: yellow;
  border-radius: 50%; /* creates a circular background */
  height: 100vh; /* makes the sun the size of the viewport */
  aspect-ratio: 1 / 1;
  animation: 4s linear 0s infinite alternate sun-rise;
}

@keyframes sun-rise {
  from {
    /* pushes the sun down past the viewport */
    transform: translateY(110vh);
  }
  to {
    /* returns the sun to its default position */
    transform: translateY(0);
  }
}
```

### Animating Multiple Properties

Adding onto the sun animation in the previous example, we add a second
animation changing the color of the sun as it rises and sets. The sun
starts off dark red when it is below the horizon and changes to a bright
orange as it reaches the top.

[html]

```html
<div class="sun"></div>
```

[css]

```css
:root {
  overflow: hidden;
  background-color: lightblue;
  display: flex;
  justify-content: center;
}

.sun {
  background-color: yellow;
  border-radius: 50%;
  height: 100vh;
  aspect-ratio: 1 / 1;
  animation: 4s linear 0s infinite alternate animating-multiple-properties;
}

/* it is possible to animate multiple properties in a single animation */
@keyframes animating-multiple-properties {
  from {
    transform: translateY(110vh);
    background-color: red;
    filter: brightness(75%);
  }
  to {
    transform: translateY(0);
    background-color: orange;
    /* unset properties i.e. 'filter' will revert to default values */
  }
}
```

### Applying Multiple Animations

Here is a sun that rises and falls on a lightblue background. The sun
gradually rotates through a rainbow of colors. The timing of the sun\'s
position and color are independent.

[html]

```html
<div class="sun"></div>
```

[css]

```css
:root {
  overflow: hidden;
  background-color: lightblue;
  display: flex;
  justify-content: center;
}

.sun {
  background-color: yellow;
  border-radius: 50%;
  height: 100vh;
  aspect-ratio: 1 / 1;
  /* multiple animations are separated by commas, each animation's parameters are set independently */
  animation:
    4s linear 0s infinite alternate rise,
    24s linear 0s infinite psychedelic;
}

@keyframes rise {
  from {
    transform: translateY(110vh);
  }
  to {
    transform: translateY(0);
  }
}

@keyframes psychedelic {
  from {
    filter: hue-rotate(0deg);
  }
  to {
    filter: hue-rotate(360deg);
  }
}
```

### Cascading Multiple Animations

Here is a yellow sun on a lightblue background. The sun bounces between
the left and right sides of the viewport. The sun remains in the
viewport even though a rise animation is defined. The rise animation\'s
transform property is \'overwritten\' by the bounce animation.

[html]

```html
<div class="sun"></div>
```

[css]

```css
:root {
  overflow: hidden;
  background-color: lightblue;
  display: flex;
  justify-content: center;
}

.sun {
  background-color: yellow;
  border-radius: 50%;
  height: 100vh;
  aspect-ratio: 1 / 1;
  /*
    animations declared later in the cascade will override the
    properties of previously declared animations
  */
  /* bounce 'overwrites' the transform set by rise, hence the sun only moves horizontally */
  animation:
    4s linear 0s infinite alternate rise,
    4s linear 0s infinite alternate bounce;
}

@keyframes rise {
  from {
    transform: translateY(110vh);
  }
  to {
    transform: translateY(0);
  }
}

@keyframes bounce {
  from {
    transform: translateX(-50vw);
  }
  to {
    transform: translateX(50vw);
  }
}
```

See [Using CSS animations](using_css_animations.md#examples)
for additional examples.

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation]](https://drafts.csswg.org/css-animations/#animation)

  -------------------------------------------------------------------------

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

`animation`

433

1212

49165

10

301512.1--1512--15

94

43

2The
[`animation-fill-mode`](https://developer.mozilla.org/docs/Web/CSS/animation-fill-mode)
property is not supported in Android browsers below 2.3.

4318

49165

301412.1--1412--14

93.2

4.01.0

`animation-timeline`

115Support is currently reset-only. Including `animation` resets a
previously-declared `animation-timeline` value to `auto`, but
`animation-timeline` cannot be set via `animation`.

115Support is currently reset-only. Including `animation` resets a
previously-declared `animation-timeline` value to `auto`, but
`animation-timeline` cannot be set via `animation`.

No

No

101Support is currently reset-only. Including `animation` resets a
previously-declared `animation-timeline` value to `auto`, but
`animation-timeline` cannot be set via `animation`.

No

115Support is currently reset-only. Including `animation` resets a
previously-declared `animation-timeline` value to `auto`, but
`animation-timeline` cannot be set via `animation`.

115Support is currently reset-only. Including `animation` resets a
previously-declared `animation-timeline` value to `auto`, but
`animation-timeline` cannot be set via `animation`.

No

NoSupport is currently reset-only. Including `animation` resets a
previously-declared `animation-timeline` value to `auto`, but
`animation-timeline` cannot be set via `animation`.

No

NoSupport is currently reset-only. Including `animation` resets a
previously-declared `animation-timeline` value to `auto`, but
`animation-timeline` cannot be set via `animation`.

See also
--------

- [Using CSS animations](using_css_animations.md)
- JavaScript
    [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
    API

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation>

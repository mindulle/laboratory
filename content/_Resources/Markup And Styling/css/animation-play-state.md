animation-play-state
====================

The `animation-play-state`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether an animation is running or paused.

Try it
------

Resuming a paused animation will start the animation from where it left
off at the time it was paused, rather than starting over from the
beginning of the animation sequence.

Syntax
------

[css]

```css
/* Single animation */
animation-play-state: running;
animation-play-state: paused;

/* Multiple animations */
animation-play-state: paused, running, running;

/* Global values */
animation-play-state: inherit;
animation-play-state: initial;
animation-play-state: revert;
animation-play-state: revert-layer;
animation-play-state: unset;
```

### Values

[`running`](#running)

:   The **animation** is currently **playing**.

[`paused`](#paused)

:   The **animation** is currently **paused**.

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they are applied to the animations in the order
in which the [`animation-name`](animation-name.md)s appear. For situations
where the number of animations and `animation-*` property values do not
match, see [](using_css_animations.md#setting_multiple_animation_property_values).

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `running`
  Applies to                         all elements, [`::before`](::before) and [`::after`](::after) [pseudo-elements](pseudo-elements.md)
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
animation-play-state = 
  <single-animation-play-state>#  

<single-animation-play-state> = 
  running  |
  paused   
```

Examples
--------

### Pausing an animation

This animation is paused, but runs when you hover over it.

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
  animation-name: rotate;
  animation-duration: 0.7s;
  animation-iteration-count: infinite;
  animation-play-state: paused;
}

.box:hover {
  animation-play-state: running;
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

Hover over the rectangle to play the animation.

See [CSS animations](using_css_animations.md) for examples.

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation-play-state]](https://drafts.csswg.org/css-animations/#animation-play-state)

  -----------------------------------------------------------------------------------------------

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

`animation-play-state`

433

1212

49165

10

301512.1--1512--15

94

43≤37

4318

49165

301412.1--1412--14

92

4.01.0

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
    [`animation-duration`](animation-duration.md),
    [`animation-fill-mode`](animation-fill-mode.md),
    [`animation-iteration-count`](animation-iteration-count.md),
    [`animation-name`](animation-name.md),
    [`animation-timeline`](animation-timeline.md),
    [`animation-timing-function`](animation-timing-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state>

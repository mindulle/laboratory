animation-iteration-count
=========================

The `animation-iteration-count`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the number of times an animation sequence should be played before
stopping.

Try it
------

It is often convenient to use the shorthand property
[`animation`](animation.md) to set all animation properties at once.

Syntax
------

[css]

```css
/* Keyword value */
animation-iteration-count: infinite;

/* <number> values */
animation-iteration-count: 3;
animation-iteration-count: 2.4;

/* Multiple values */
animation-iteration-count: 2, 0, infinite;

/* Global values */
animation-iteration-count: inherit;
animation-iteration-count: initial;
animation-iteration-count: revert;
animation-iteration-count: revert-layer;
animation-iteration-count: unset;
```

The `animation-iteration-count` property is specified as one or more
comma-separated values.

### Values

[`infinite`](#infinite)

:   The animation will repeat forever.

`<number>`

:   The number of times the animation will repeat; this is `1` by
    default. You may specify non-integer values to play part of an
    animation cycle: for example, `0.5` will play half of the animation
    cycle. Negative values are invalid.

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they are applied to the animations in the order
in which the [`animation-name`](animation-name.md)s appear. For situations
where the number of animations and `animation-*` property values do not
match, see [](using_css_animations.md#setting_multiple_animation_property_values).

**Note:** When creating [](css_scroll-driven_animations.md), specifying an
`animation-iteration-count` causes the animation to repeat that number
of times over the course of the timeline\'s progression. If an
`animation-iteration-count` is not provided, the animation will only
occur once. `infinite` is a valid value for scroll-driven animations,
but it results in an animation that doesn\'t work.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `1`
  Applies to                         all elements, [`::before`](::before) and [`::after`](::after) [pseudo-elements](pseudo-elements.md)
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
animation-iteration-count = 
  <single-animation-iteration-count>#  

<single-animation-iteration-count> = 
  infinite        |
  <number [0,∞]>  
```

Examples
--------

### Setting iteration count

This animation will run 10 times.

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
  animation-iteration-count: 10;
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

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation-iteration-count]](https://drafts.csswg.org/css-animations/#animation-iteration-count)

  ---------------------------------------------------------------------------------------------------------

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

`animation-iteration-count`

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
    [`animation-delay`](animation-delay.md),
    [`animation-direction`](animation-direction.md),
    [`animation-duration`](animation-duration.md),
    [`animation-fill-mode`](animation-fill-mode.md),
    [`animation-name`](animation-name.md),
    [`animation-play-state`](animation-play-state.md),
    [`animation-timeline`](animation-timeline.md),
    [`animation-timing-function`](animation-timing-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count>

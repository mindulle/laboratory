animation-direction
===================

The `animation-direction`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether an animation should play forward, backward, or alternate back
and forth between playing the sequence forward and backward.

Try it
------

It is often convenient to use the shorthand property
[`animation`](animation.md) to set all animation properties at once.

Syntax
------

[css]

```css
/* Single animation */
animation-direction: normal;
animation-direction: reverse;
animation-direction: alternate;
animation-direction: alternate-reverse;

/* Multiple animations */
animation-direction: normal, reverse;
animation-direction: alternate, reverse, normal;

/* Global values */
animation-direction: inherit;
animation-direction: initial;
animation-direction: revert;
animation-direction: revert-layer;
animation-direction: unset;
```

### Values

[`normal`](#normal)

:   The animation plays *forwards* each cycle. In other words, each time
    the animation cycles, the animation will reset to the beginning
    state and start over again. This is the default value.

[`reverse`](#reverse)

:   The animation plays *backwards* each cycle. In other words, each
    time the animation cycles, the animation will reset to the end state
    and start over again. Animation steps are performed backwards, and
    easing functions are also reversed. For example, an `ease-in` easing
    function becomes `ease-out`.

[`alternate`](#alternate)

:   The animation reverses direction each cycle, with the first
    iteration being played *forwards*. The count to determine if a cycle
    is even or odd starts at one.

[`alternate-reverse`](#alternate-reverse)

:   The animation reverses direction each cycle, with the first
    iteration being played *backwards*. The count to determine if a
    cycle is even or odd starts at one.

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they are applied to the animations in the order
in which the [`animation-name`](animation-name.md)s appear. For situations
where the number of animations and `animation-*` property values do not
match, see [](using_css_animations.md#setting_multiple_animation_property_values).

**Note:** When creating [](css_scroll-driven_animations.md), specifying an
`animation-direction` works as expected, for example `reverse` causes
the animation to run in reverse over the course of the timeline\'s
progression. A value of `alternate` (combined with an
[`animation-iteration-count`](animation-iteration-count.md)) causes the
animation to run forwards and backwards as the timeline is progressed.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements, [`::before`](::before) and [`::after`](::after) [pseudo-elements](pseudo-elements.md)
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
animation-direction = 
  <single-animation-direction>#  

<single-animation-direction> = 
  normal             |
  reverse            |
  alternate          |
  alternate-reverse  
```

Examples
--------

### Reversing the animation direction

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
  animation-direction: reverse;
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

See [CSS animations](using_css_animations.md) for examples.

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation-direction]](https://drafts.csswg.org/css-animations/#animation-direction)

  ---------------------------------------------------------------------------------------------

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

`animation-direction`

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

`alternate-reverse`

19

12

16

10

12.1

6

4.4

25

16

12.1

6

1.5

`reverse`

19

12

16

10

12.1

6

4.4

25

16

12.1

6

1.5

See also
--------

- [Using CSS animations](using_css_animations.md)
- JavaScript
    [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
    API
- Other related animation properties: [`animation`](animation.md),
    [`animation-composition`](animation-composition.md),
    [`animation-delay`](animation-delay.md),
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
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction>

animation-fill-mode
===================

The `animation-fill-mode`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how a CSS animation applies styles to its target before and after its
execution.

Try it
------

It is often convenient to use the shorthand property
[`animation`](animation.md) to set all animation properties at once.

Syntax
------

[css]

```css
/* Single animation */
animation-fill-mode: none;
animation-fill-mode: forwards;
animation-fill-mode: backwards;
animation-fill-mode: both;

/* Multiple animations */
animation-fill-mode: none, backwards;
animation-fill-mode: both, forwards, none;

/* Global values */
animation-fill-mode: inherit;
animation-fill-mode: initial;
animation-fill-mode: revert;
animation-fill-mode: revert-layer;
animation-fill-mode: unset;
```

### Values

[`none`](#none)

:   The animation will not apply any styles to the target when it\'s not
    executing. The element will instead be displayed using any other CSS
    rules applied to it. This is the default value.

[`forwards`](#forwards)

:   The target will retain the computed values set by the last
    [keyframe](@keyframes.md) encountered during execution. The last
    keyframe depends on the value of
    [`animation-direction`](animation-direction.md) and
    [`animation-iteration-count`](animation-iteration-count.md):

      `animation-direction`   `animation-iteration-count`   last keyframe encountered
      ----------------------- ----------------------------- ---------------------------
      `normal`                even or odd                   `100%` or `to`
      `reverse`               even or odd                   `0%` or `from`
      `alternate`             even                          `0%` or `from`
      `alternate`             odd                           `100%` or `to`
      `alternate-reverse`     even                          `100%` or `to`
      `alternate-reverse`     odd                           `0%` or `from`

[`backwards`](#backwards)

:   The animation will apply the values defined in the first relevant
    [keyframe](@keyframes.md) as soon as it is applied to the target, and
    retain this during the [`animation-delay`](animation-delay.md) period.
    The first relevant keyframe depends on the value of
    [`animation-direction`](animation-direction.md):

      `animation-direction`              first relevant keyframe
      ---------------------------------- -------------------------
      `normal` or `alternate`            `0%` or `from`
      `reverse` or `alternate-reverse`   `100%` or `to`

[`both`](#both)

:   The animation will follow the rules for both forwards and backwards,
    thus extending the animation properties in both directions.

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they are applied to the animations in the order
in which the [`animation-name`](animation-name.md)s appear. For situations
where the number of animations and `animation-*` property values do not
match, see [](using_css_animations.md#setting_multiple_animation_property_values).

**Note:** `animation-fill-mode` has the same effect when creating [](css_scroll-driven_animations.md) as it does for
regular time-based animations.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements, [`::before`](::before) and [`::after`](::after) [pseudo-elements](pseudo-elements.md)
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
animation-fill-mode = 
  <single-animation-fill-mode>#  

<single-animation-fill-mode> = 
  none       |
  forwards   |
  backwards  |
  both       
```

Examples
--------

### Setting fill mode

You can see the effect of `animation-fill-mode` in the following
example. It demonstrates how you can make the animation remain in its
final state rather than reverting to the original state (which is the
default).

#### HTML

[html]

```html
<p>Move your mouse over the gray box!</p>
<div class="demo">
  <div class="growsandstays">This grows and stays big.</div>
  <div class="grows">This just grows.</div>
</div>
```

#### CSS

[css]

```css
.demo {
  border-top: 100px solid #ccc;
  height: 300px;
}

@keyframes grow {
  0% {
    font-size: 0;
  }
  100% {
    font-size: 40px;
  }
}

.demo:hover .grows {
  animation-name: grow;
  animation-duration: 3s;
}

.demo:hover .growsandstays {
  animation-name: grow;
  animation-duration: 3s;
  animation-fill-mode: forwards;
}
```

#### Result

See [CSS animations](using_css_animations.md) for more
examples.

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation-fill-mode]](https://drafts.csswg.org/css-animations/#animation-fill-mode)

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

`animation-fill-mode`

433

1212

49165

10

301512.1--1512--15

95

43≤37

4318

49165

301412.1--1412--14

94

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
    [`animation-iteration-count`](animation-iteration-count.md),
    [`animation-name`](animation-name.md),
    [`animation-play-state`](animation-play-state.md),
    [`animation-timeline`](animation-timeline.md),
    [`animation-timing-function`](animation-timing-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode>

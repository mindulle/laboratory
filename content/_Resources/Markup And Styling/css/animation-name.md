animation-name
==============

The `animation-name`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the names of one or more [`@keyframes`](@keyframes.md) at-rules
that describe the animation to apply to an element. Multiple `@keyframe`
at-rules are specified as a comma-separated list of names. If the
specified name does not match any `@keyframe` at-rule, no properties are
animated.

Try it
------

It is often convenient to use the shorthand property
[`animation`](animation.md) to set all animation properties at once.

Syntax
------

[css]

```css
/* Single animation */
animation-name: none;
animation-name: test_05;
animation-name: -specific;
animation-name: sliding-vertically;

/* Multiple animations */
animation-name: test1, animation4;
animation-name:
  none,
  -moz-specific,
  sliding;

/* Global values */
animation-name: inherit;
animation-name: initial;
animation-name: revert;
animation-name: revert-layer;
animation-name: unset;
```

### Values

[`none`](#none)

:   A special keyword denoting no keyframes. It can be used to
    deactivate an animation without changing the ordering of the other
    identifiers, or to deactivate animations coming from the cascade.

[`<custom-ident>`](custom-ident.md)

:   A name identifying the animation. This identifier is composed of a
    combination of case-sensitive letters `a` to `z`, numbers `0` to
    `9`, underscores (`_`), and/or dashes (`-`). The first non-dash
    character must be a letter. Also, two dashes are forbidden at the
    beginning of the identifier. Furthermore, the identifier can\'t be
    `none`, `unset`, `initial`, or `inherit`.

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they are applied to the animations in the order
in which the [`animation-name`](animation-name.md)s appear. For situations
where the number of animations and `animation-*` property values do not
match, see [](using_css_animations.md#setting_multiple_animation_property_values).

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
animation-name = 
  [ none | <keyframes-name> ]#  

<keyframes-name> = 
  <custom-ident>  |
  <string>        
```

Examples
--------

### Naming an animation

This animation has an `animation-name` of `rotate`.

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

See [CSS animations](using_css_animations.md) for examples.

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  animation-name]](https://drafts.csswg.org/css-animations/#animation-name)

  -----------------------------------------------------------------------------------

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

`animation-name`

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
    [`animation-iteration-count`](animation-iteration-count.md),
    [`animation-play-state`](animation-play-state.md),
    [`animation-timeline`](animation-timeline.md),
    [`animation-timing-function`](animation-timing-function.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name>

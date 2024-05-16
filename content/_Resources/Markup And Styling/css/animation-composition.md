animation-composition
=====================

The `animation-composition`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the [composite
operation](https://developer.mozilla.org/en-US/docs/Glossary/Composite_operation)
to use when multiple animations affect the same property simultaneously.

Syntax
------

[css]

```css
/* Single animation */
animation-composition: replace;
animation-composition: add;
animation-composition: accumulate;

/* Multiple animations */
animation-composition: replace, add;
animation-composition: add, accumulate;
animation-composition: replace, add, accumulate;

/* Global values */
animation-composition: inherit;
animation-composition: initial;
animation-composition: revert;
animation-composition: revert-layer;
animation-composition: unset;
```

**Note:** When you specify multiple comma-separated values on an
`animation-*` property, they will be applied to the animations in the
order in which the [`animation-name`](animation-name.md)s appear. If the
number of animations and compositions differ, the values listed in the
`animation-composition` property will cycle from the first to the last
`animation-name`, looping until all the animations have an assigned
`animation-composition` value. For more information, see [](using_css_animations.md#setting_multiple_animation_property_values).

### Values

[`replace`](#replace)

:   The effect value overrides the underlying value of the property.
    This is the default value.

[`add`](#add)

:   The effect value builds on the underlying value of the property.
    This operation produces an additive effect. For animation types
    where the addition operation is not commutative, the order of the
    operands is the underlying value followed by the effect value.

[`accumulate`](#accumulate)

:   The effect and underlying values are combined. For animation types
    where the addition operation is not commutative, the order of the
    operands is the underlying value followed by the effect value.

Description
-----------

Each property that is targeted by the [\@keyframes](@keyframes.md) at-rule
is associated with an effect stack. The value of the effect stack is
calculated by combining the *underlying value* of a property in a CSS
style rule with the *effect value* of that property in the keyframe. The
`animation-composition` property helps to specify how to combine the
underlying value with the effect value.

For example, in the CSS below, `blur(5px)` is the underlying value, and
`blur(10px)` is the effect value. The `animation-composition` property
specifies the operation to perform to produce the final effect value
after compositing the effect of the underlying value and the effect
value.

[css]

```css
.icon:hover {
  filter: blur(5px);
  animation: 3s infinite pulse;
  animation-composition: add;
}

@keyframes pulse {
  0% {
    filter: blur(10px);
  }
  100% {
    filter: blur(20px);
  }
}
```

Consider different values for the `animation-composition` property in
the above example. The final effect value in each of those cases will be
calculated as explained below:

- With `replace`, `blur(10px)` will replace `blur(5px)` in the `0%`
    keyframe. This is the default behavior of the property.
- With `add`, the composite effect value in the `0%` keyframe will be
    `blur(5px) blur(10px)`.
- With `accumulate`, the composite effect value in `0%` keyframe will
    be `blur(15px)`.

**Note:** A composite operation can also be specified in a keyframe. In
that case, the specified composite operation is used for each property
first within that keyframe and then on each property in the next
keyframe.

Formal definition
-----------------

  ---------------------------------- ----------------
  [Initial value](initial_value.md)     `replace`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- ----------------

Formal syntax
-------------

```
animation-composition = 
  <single-animation-composition>#  

<single-animation-composition> = 
  replace     |
  add         |
  accumulate  
```

Examples
--------

### Understanding the animation-composition values

The example below shows the effect of different `animation-composition`
values side-by-side.

#### HTML

[html]

```html
<div class="container">
  replace
  <div id="replace" class="target"></div>
</div>
<div class="container">
  add
  <div id="add" class="target"></div>
</div>
<div class="container">
  accumulate
  <div id="accumulate" class="target"></div>
</div>
```

#### CSS

Here the underlying value is `translateX(50px) rotate(45deg)`.

[css]

```css
@keyframes slide {
  20%,
  40% {
    transform: translateX(100px);
    background: yellow;
  }
  80%,
  100% {
    transform: translateX(150px);
    background: orange;
  }
}

.target {
  transform: translateX(30px) rotate(45deg);
  animation: slide 5s linear infinite;
}
.target:hover {
  animation-play-state: paused;
}
#replace {
  animation-composition: replace;
}
#add {
  animation-composition: add;
}
#accumulate {
  animation-composition: accumulate;
}
```

#### Result

- With `replace`, the final effect value for the `transform` property
    in the `0%, 20%` keyframe is `translateX(100px)` (completely
    replacing the underlying value `translateX(30px) rotate(45deg)`). In
    this case, the element rotates from 45deg to 0deg as it animates
    from the default value set on the element itself to the non-rotated
    value set at the 0% mark. This is the default behavior.
- With `add`, the final effect value for the `transform` property in
    the `0%, 20%` keyframe is `translateX(30px) rotate(45deg)` followed
    by `translateX(100px)`. So the element is moved `30px` to the right,
    rotated `45deg`, then translated `100px` more along the redirected X
    axis.
- With `accumulate`, the final effect value in the `0%, 20%` keyframe
    is `translateX(130px) rotate(45deg)`. This means that the two X-axis
    translation values of `30px` and `100px` are combined or
    \"accumulated\".

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [CSS Animations Level 2\
  [\#
  animation-composition]](https://drafts.csswg.org/css-animations-2/#animation-composition)

  ---------------------------------------------------------------------------------------------------

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

`animation-composition`

112

112

115

No

98

16

112

112

115

No

16

No

See also
--------

- [Using CSS animations](using_css_animations.md)
- [Composite property of
    KeyFrameEffect](https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/composite)
- Other related animation properties: [`animation`](animation.md),
    [`animation-delay`](animation-delay.md),
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
https://developer.mozilla.org/en-US/docs/Web/CSS/animation-composition>

CSS animations
==============

The **CSS animations** module lets you animate the values of CSS
properties, such as background-position and transform, over time by
using keyframes. Each keyframe describes how the animated element should
render at a given time during the animation sequence. You can use the
properties in the animations module to control the duration, number of
repetitions, delayed start, and other aspects of an animation.

### Animations in action

To view the animation in the box below, click the checkbox \'Play the
animation\' or hover the cursor over the box. When the animating is
active, the cloud at the top changes shape, snowflakes fall, and the
snow level at the bottom rises. To pause the animation, uncheck the
checkbox or move your cursor away from the box.

This sample animation uses
[`animation-iteration-count`](animation-iteration-count.md) to make the
flakes fall repeatedly, [`animation-direction`](animation-direction.md) to
make the cloud move back and forth,
[`animation-fill-mode`](animation-fill-mode.md) to raise the snow level in
response to the cloud movement, and
[`animation-play-state`](animation-play-state.md) to pause the animation.

To see the code for this animation, [view the source on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/animation.html).

Reference
---------

### Properties

- [`animation`](animation.md) shorthand
- [`animation-composition`](animation-composition.md)
- [`animation-delay`](animation-delay.md)
- [`animation-direction`](animation-direction.md)
- [`animation-duration`](animation-duration.md)
- [`animation-fill-mode`](animation-fill-mode.md)
- [`animation-iteration-count`](animation-iteration-count.md)
- [`animation-name`](animation-name.md)
- [`animation-play-state`](animation-play-state.md)
- [`animation-timing-function`](animation-timing-function.md)
- [`animation-timeline`](animation-timeline.md)

### At-rules

- [`@keyframes`](@keyframes.md)

### Events

All animations, even those with 0 seconds duration, throw animation
events.

- [`animationstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationstart_event)
- [`animationend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationend_event)
- [`animationcancel`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationcancel_event)
- [`animationiteration`](https://developer.mozilla.org/en-US/docs/Web/API/Element/animationiteration_event)

### Interfaces

- [Web Animations
    API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Animations_API)
- [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)
- [`CSSKeyframeRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframeRule)
- [`CSSKeyframesRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule)

Guides
------

[Using CSS animations](using_css_animations.md)

:   Step-by-step tutorial on how to create animations using CSS. This
    article describes the animation-related CSS properties and at-rule
    and how they interact with each other.

[CSS animation tips and tricks](tips.md)

:   Tips and tricks to help you get the most out of CSS animations.

Related concepts
----------------

- [`will-change`](will-change.md) CSS property
- [`<easing-function>`](easing-function.md) data type
- [`prefers-reduced-motion`](prefers-reduced-motion.md) media
    query
- [Bezier
    curve](https://developer.mozilla.org/en-US/docs/Glossary/Bezier_curve)
    glossary term

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Animations Level 2\
  ](https://drafts.csswg.org/css-animations-2/)

[CSS Animations Level 1\
  ](https://drafts.csswg.org/css-animations/)
  -----------------------------------------------------------------------

See also
--------

- [CSS scroll-driven animations](css_scroll-driven_animations.md)
- Properties in the [transitions](css_transitions.md) CSS module to
    trigger animations based on user actions
- The
    [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)
    HTML element along with [canvas
    API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
    and [WebGL
    API](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API) to
    draw graphics and animations
- The
    [`SVGAnimationElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimationElement)
    interface for all the animation-related element interfaces,
    including
    [`SVGAnimateElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimateElement),
    [`SVGSetElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGSetElement),
    [`SVGAnimateColorElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimateColorElement),
    [`SVGAnimateMotionElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimateMotionElement),
    and
    [`SVGAnimateTransformElement`](https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimateTransformElement)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animations>

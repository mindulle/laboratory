\@keyframes
===========

The `@keyframes` CSS [at-rule](at-rule.md) controls the intermediate steps
in a CSS animation sequence by defining styles for keyframes (or
waypoints) along the animation sequence. This gives more control over
the intermediate steps of the animation sequence than
[transitions](css_transitions.md).

Syntax
------

[css]

```css
@keyframes slidein {
  from {
    transform: translateX(0%);
  }

  to {
    transform: translateX(100%);
  }
}
```

### Values

[`<custom-ident>`](custom-ident.md)

:   A name identifying the keyframe list. This must match the identifier
    production in CSS syntax.

[`from`](#from)

:   A starting offset of `0%`.

[`to`](#to)

:   An ending offset of `100%`.

[`<percentage>`](percentage.md)

:   A percentage of the time through the animation sequence at which the
    specified keyframe should occur.

[`<timeline-range-name>`](#timeline-range-name) [`<percentage>`](percentage.md) [Experimental]

:   A percentage of the time through the specified
    [`animation-range`](animation-range.md) at which the specified keyframe
    should occur. See [](css_scroll-driven_animations.md) for more information on
    the kinds of animations that use named timeline ranges.

Description
-----------

To use keyframes, create a `@keyframes` rule with a name that is then
used by the [`animation-name`](animation-name.md) property to match an
animation to its keyframe declaration. Each `@keyframes` rule contains a
style list of keyframe selectors, which specify percentages along the
animation when the keyframe occurs, and a block containing the styles
for that keyframe.

You can list the keyframe percentages in any order; they will be handled
in the order they should occur.

JavaScript can access the `@keyframes` at-rule with the CSS object model
interface
[`CSSKeyframesRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSKeyframesRule).

### Valid keyframe lists

If a keyframe rule doesn\'t specify the start or end states of the
animation (that is, `0%`/`from` and `100%`/`to`), browsers will use the
element\'s existing styles for the start/end states. This can be used to
animate an element from its initial state and back.

Properties that can\'t be animated in keyframe rules are ignored, but
supported properties will still be animated.

### Resolving duplicates

If multiple keyframe sets exist for a given name, the last one
encountered by the parser is used. `@keyframes` rules don\'t cascade, so
animations never derive keyframes from more than one rule set.

If a given animation time offset is duplicated, all keyframes in the
`@keyframes` rule for that percentage are used for that frame. There is
cascading within a `@keyframes` rule if multiple keyframes specify the
same percentage values.

### When properties are left out of some keyframes

Properties that aren\'t specified in every keyframe are interpolated if
possible --- properties that can\'t be interpolated are dropped from the
animation. For example:

[css]

```css
@keyframes identifier {
  0% {
    top: 0;
    left: 0;
  }
  30% {
    top: 50px;
  }
  68%,
  72% {
    left: 50px;
  }
  100% {
    top: 100px;
    left: 100%;
  }
}
```

Here, the [`top`](top.md) property animates using the `0%`, `30%`, and
`100%` keyframes, and [`left`](left.md) animates using the `0%`, `68%`,
`72%` and `100%` keyframes.

### When a keyframe is defined multiple times

If a keyframe is defined multiple times but not all affected properties
are in each keyframe, all values specified in these keyframes are
considered. For example:

[css]

```css
@keyframes identifier {
  0% {
    top: 0;
  }
  50% {
    top: 30px;
    left: 20px;
  }
  50% {
    top: 10px;
  }
  100% {
    top: 0;
  }
}
```

In this example, at the `50%` keyframe, the values used are `top: 10px`
and `left: 20px`.

Cascading keyframes are supported starting in Firefox 14.

### `!important` in a keyframe

Declarations in a keyframe qualified with `!important` are ignored.

[css]

```css
@keyframes important1 {
  from {
    margin-top: 50px;
  }
  50% {
    margin-top: 150px !important;
  } /* ignored */
  to {
    margin-top: 100px;
  }
}

@keyframes important2 {
  from {
    margin-top: 50px;
    margin-bottom: 100px;
  }
  to {
    margin-top: 150px !important; /* ignored */
    margin-bottom: 50px;
  }
}
```

Formal syntax
-------------

```
@keyframes = 
  @keyframes <keyframes-name>   

<keyframes-name> = 
  <custom-ident>  |
  <string>        
```

Examples
--------

### CSS animation examples

See [Using CSS animations](using_css_animations.md) and
[Animate elements on scroll with Scroll-driven
animations](https://developer.chrome.com/articles/scroll-driven-animations/)
for examples.

Specifications
--------------

  -------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------

  [CSS Animations Level 1\
  [\#
  keyframes]](https://drafts.csswg.org/css-animations/#keyframes)

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

`@keyframes`

431

12

49165

10

301512.1--1512--15

94

434.4

4318

49165

301412.1--1412--14

94

4.01.0

`ignore_important_declarations`

45

79

19

No

32

10.1

45

45

19

32

10.3

5.0

`named_range_keyframes`

115

115

No

No

101

No

115

115

No

No

No

No

See also
--------

- [`animation-range`](animation-range.md)
- [CSS scroll-driven animations](css_scroll-driven_animations.md)
- [Using CSS animations](using_css_animations.md)
- [Animate elements on scroll with Scroll-driven
    animations](https://developer.chrome.com/articles/scroll-driven-animations/)
- [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes>

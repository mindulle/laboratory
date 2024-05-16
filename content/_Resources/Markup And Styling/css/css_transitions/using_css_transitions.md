Using CSS transitions
=====================

**CSS transitions** provide a way to control animation speed when
changing CSS properties. Instead of having property changes take effect
immediately, you can cause the changes in a property to take place over
a period of time. For example, if you change the color of an element
from white to black, usually the change is instantaneous. With CSS
transitions enabled, changes occur at time intervals that follow an
acceleration curve, all of which can be customized.

Animations that involve transitioning between two states are often
called *implicit transitions* as the states in between the start and
final states are implicitly defined by the browser.

CSS transitions let you decide which properties to animate (by [](transition-property.md)), when the animation will
start (by setting a [*delay*](transition-delay.md)), how long the
transition will last (by setting a
[*duration*](transition-duration.md)), and how the transition will run
(by defining an [*easing function*](transition-timing-function.md),
e.g., linearly or quick at the beginning, slow at the end).

Which CSS properties can be transitioned?
-----------------------------------------

The Web author can define which property has to be animated and in which
way. This allows the creation of complex transitions. However, some
properties are [not animatable](css_animated_properties.md) as it
doesn\'t make sense to animate them.

**Note:** The `auto` value is often a very complex case. The
specification recommends not animating from and to `auto`. Some user
agents, like those based on Gecko, implement this requirement and
others, like those based on WebKit, are less strict. Using animations
with `auto` may lead to unpredictable results, depending on the browser
and its version, and should be avoided.

Defining transitions
--------------------

CSS Transitions are controlled using the shorthand
[`transition`](transition.md) property. This is the best way to
configure transitions, as it makes it easier to avoid out of sync
parameters, which can be very frustrating to have to spend lots of time
debugging in CSS.

You can control the individual components of the transition with the
following sub-properties:

[`transition-property`](transition-property.md)

:   Specifies the name or names of the CSS properties to which
    transitions should be applied. Only properties listed here are
    animated during transitions; changes to all other properties occur
    instantaneously as usual.

[`transition-duration`](transition-duration.md)

:   Specifies the duration over which transitions should occur. You can
    specify a single duration that applies to all properties during the
    transition, or multiple values to allow each property to transition
    over a different period of time.

[`transition-timing-function`](transition-timing-function.md)

:   Specifies a function to define how intermediate values for
    properties are computed. *Easing functions* determine how
    intermediate values of the transition are calculated. Most [](easing-function.md) can be specified by providing the
    graph of the corresponding function, as defined by four points
    defining a cubic bezier. You can also choose easing from [Easing
    functions cheat sheet](https://easings.net/).

[`transition-delay`](transition-delay.md)

:   Defines how long to wait between the time a property is changed and
    the transition actually begins.

The `transition` shorthand CSS syntax is written as follows:

[css]

```css
div {
  transition: <property> <duration> <timing-function> <delay>;
}
```

Examples
--------

### Simple example

This example performs a four-second font size transition with a
two-second delay between the time the user mouses over the element and
the beginning of the animation effect:

[css]

```css
#delay {
  font-size: 14px;
  transition-property: font-size;
  transition-duration: 4s;
  transition-delay: 2s;
}

#delay:hover {
  font-size: 36px;
}
```

### Multiple animated properties example

#### CSS

[css]

```css
.box {
  border-style: solid;
  border-width: 1px;
  display: block;
  width: 100px;
  height: 100px;
  background-color: #0000ff;
  transition:
    width 2s,
    height 2s,
    background-color 2s,
    rotate 2s;
}

.box:hover {
  background-color: #ffcccc;
  width: 200px;
  height: 200px;
  rotate: 180deg;
}
```

### When property value lists are of different lengths

If any property\'s list of values is shorter than the others, its values
are repeated to make them match. For example:

[css]

```css
div {
  transition-property: opacity, left, top, height;
  transition-duration: 3s, 5s;
}
```

This is treated as if it were:

[css]

```css
div {
  transition-property: opacity, left, top, height;
  transition-duration: 3s, 5s, 3s, 5s;
}
```

Similarly, if any property\'s value list is longer than that for
[`transition-property`](transition-property.md), it\'s truncated, so if
you have the following CSS:

[css]

```css
div {
  transition-property: opacity, left;
  transition-duration: 3s, 5s, 2s, 1s;
}
```

This gets interpreted as:

[css]

```css
div {
  transition-property: opacity, left;
  transition-duration: 3s, 5s;
}
```

### Using transitions when highlighting menus

A common use of CSS is to highlight items in a menu as the user hovers
the mouse cursor over them. It\'s easy to use transitions to make the
effect even more attractive.

First, we set up the menu using HTML:

[html]

```html
<nav>
  <a href="#">Home</a>
  <a href="#">About</a>
  <a href="#">Contact Us</a>
  <a href="#">Links</a>
</nav>
```

Then we build the CSS to implement the look and feel of our menu:

[css]

```css
nav {
  display: flex;
  gap: 0.5rem;
}

a {
  flex: 1;
  background-color: #333;
  color: #fff;
  border: 1px solid;
  padding: 0.5rem;
  text-align: center;
  text-decoration: none;
  transition: all 0.5s ease-out;
}

a:hover,
a:focus {
  background-color: #fff;
  color: #333;
}
```

This CSS establishes the look of the menu, with the background and text
colors both changing when the element is in its [`:hover`](../:hover)
and [`:focus`](../:focus) states:

JavaScript examples
-------------------

**Note:** Care should be taken when using a transition immediately
after:

- adding the element to the DOM using `.appendChild()`
- removing an element\'s `display: none;` property.

This is treated as if the initial state had never occurred and the
element was always in its final state. The easy way to overcome this
limitation is to apply a `setTimeout()` of a handful of milliseconds
before changing the CSS property you intend to transition to.

### Using transitions to make JavaScript functionality smooth

Transitions are a great tool to make things look much smoother without
having to do anything to your JavaScript functionality. Take the
following example.

[html]

```html
<p>Click anywhere to move the ball</p>
<div id="foo" class="ball"></div>
```

Using JavaScript you can make the effect of moving the ball to a certain
position happen:

[js]

```js
const f = document.getElementById("foo");
document.addEventListener(
  "click",
  (ev) => {
    f.style.transform = `translateY($px)`;
    f.style.transform += `translateX($px)`;
  },
  false,
);
```

With CSS you can make it smooth without any extra effort. Add a
transition to the element and any change will happen smoothly:

[css]

```css
.ball {
  border-radius: 25px;
  width: 50px;
  height: 50px;
  background: #c00;
  position: absolute;
  top: 0;
  left: 0;
  transition: transform 1s;
}
```

### Detecting the start and completion of a transition

You can use the
[`transitionend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/transitionend_event)
event to detect that an animation has finished running. This is a
[`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)
object, which has two added properties beyond a typical
[`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event)
object:

[`propertyName`](#propertyname)

:   A string indicating the name of the CSS property whose transition
    completed.

[`elapsedTime`](#elapsedtime)

:   A float indicating the number of seconds the transition had been
    running at the time the event fired. This value isn\'t affected by
    the value of [`transition-delay`](transition-delay.md).

As usual, you can use the
[`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener)
method to monitor for this event:

[js]

```js
el.addEventListener("transitionend", updateTransition, true);
```

You detect the beginning of a transition using
[`transitionrun`](https://developer.mozilla.org/en-US/docs/Web/API/Element/transitionrun_event)
(fires before any delay) and
[`transitionstart`](https://developer.mozilla.org/en-US/docs/Web/API/Element/transitionstart_event)
(fires after any delay), in the same kind of fashion:

[js]

```js
el.addEventListener("transitionrun", signalStart, true);
el.addEventListener("transitionstart", signalStart, true);
```

**Note:** The `transitionend` event doesn\'t fire if the transition is
aborted before the transition is completed because either the element is
made [`display`](display.md)`: none` or the animating property\'s value
is changed.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Transitions\
  ](https://drafts.csswg.org/css-transitions/)

  -----------------------------------------------------------------------

See also
--------

- The
    [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)
    interface and the
    [`transitionend`](https://developer.mozilla.org/en-US/docs/Web/API/Element/transitionend_event)
    event
- [Using CSS animations](using_css_animations.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_transitions/Using_CSS_transitions>

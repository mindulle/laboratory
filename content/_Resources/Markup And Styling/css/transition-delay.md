transition-delay
================

The `transition-delay` CSS property specifies the duration to wait
before starting a property\'s [](using_css_transitions.md) when its value changes.

Try it
------

The delay may be zero, positive, or negative:

- A value of `0s` (or `0ms`) will begin the transition effect
    immediately.
- A positive value will delay the start of the transition effect for
    the given length of time.
- A negative value will begin the transition effect immediately, and
    partway through the effect. In other words, the effect will be
    animated as if it had already been running for the given length of
    time.

You may specify multiple delays, which is useful when transitioning
multiple properties. Each delay will be applied to the corresponding
property as specified by the
[`transition-property`](transition-property.md) property, which acts as a
master list. If there are fewer delays specified than in the master
list, the list of delay values will be repeated until there are enough.
If there are more delays, the list of delay values will be truncated to
match the number of properties. In both cases, the CSS declaration
remains valid.

Syntax
------

[css]

```css
/* <time> values */
transition-delay: 3s;
transition-delay: 2s, 4ms;

/* Global values */
transition-delay: inherit;
transition-delay: initial;
transition-delay: revert;
transition-delay: revert-layer;
transition-delay: unset;
```

### Values

[`<time>`](time.md)

:   Denotes the amount of time to wait between a property\'s value
    changing and the start of the transition effect.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0s`
  Applies to                         all elements, [`::before`](::before) and [`::after`](::after) [pseudo-elements](pseudo-elements.md)
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- --------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
transition-delay = 
  <time>#  
```

Examples
--------

### Example showing different delays

#### HTML

[html]

```html
<div class="box delay-1">0.5 seconds</div>

<div class="box delay-2">2 seconds</div>

<div class="box delay-3">4 seconds</div>

<button id="change">Change</button>
```

#### CSS

[css]

```css
.box {
  margin: 20px;
  padding: 10px;
  display: inline-block;
  width: 100px;
  height: 100px;
  background-color: red;
  font-size: 18px;
  transition-property: background-color, font-size, transform, color;
  transition-timing-function: ease-in-out;
  transition-duration: 3s;
}

.transformed-state {
  transform: rotate(270deg);
  background-color: blue;
  color: yellow;
  font-size: 12px;
  transition-property: background-color, font-size, transform, color;
  transition-timing-function: ease-in-out;
  transition-duration: 3s;
}

.delay-1 {
  transition-delay: 0.5s;
}

.delay-2 {
  transition-delay: 2s;
}

.delay-3 {
  transition-delay: 4s;
}
```

#### JavaScript

[js]

```js
function change() {
  const elements = document.querySelectorAll("div.box");
  for (const element of elements) {
    element.classList.toggle("transformed-state");
  }
}

const changeButton = document.querySelector("#change");
changeButton.addEventListener("click", change);
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [CSS Transitions\
  [\#
  transition-delay-property]](https://drafts.csswg.org/css-transitions/#transition-delay-property)

  ----------------------------------------------------------------------------------------------------------

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

`transition-delay`

261

1212

49164

1010

1512.111.6--15

94

4.42

2618

49164

1412.112--14

92

1.51.0

See also
--------

- [Using CSS transitions](using_css_transitions.md)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)
    API

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay>

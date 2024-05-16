transition-duration
===================

The `transition-duration`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the length of time a transition animation should take to complete. By
default, the value is `0s`, meaning that no animation will occur.

Try it
------

You may specify multiple durations; each duration will be applied to the
corresponding property as specified by the
[`transition-property`](transition-property.md) property, which acts as a
master list. If the number of specified durations is less than in the
master list, the user agent repeats the list of durations. If the number
of specified durations is more than in the master list, the list is
truncated to the right size. In both the cases, the CSS declaration
stays valid.

Syntax
------

[css]

```css
/* <time> values */
transition-duration: 6s;
transition-duration: 120ms;
transition-duration: 1s, 15s;
transition-duration: 10s, 30s, 230ms;

/* Global values */
transition-duration: inherit;
transition-duration: initial;
transition-duration: revert;
transition-duration: revert-layer;
transition-duration: unset;
```

### Values

[`<time>`](#time)

:   Is a [`<time>`](time.md) denoting the amount of time the transition
    from the old value of a property to the new value should take. A
    time of `0s` indicates that no transition will happen, that is the
    switch between the two states will be instantaneous. A negative
    value for the time renders the declaration invalid.

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
transition-duration = 
  <time [0s,∞]>#  
```

Examples
--------

### Example showing different durations

#### HTML

[html]

```html
<div class="box duration-1">0.5 seconds</div>

<div class="box duration-2">2 seconds</div>

<div class="box duration-3">4 seconds</div>

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
}

.transformed-state {
  transform: rotate(270deg);
  background-color: blue;
  color: yellow;
  font-size: 12px;
  transition-property: background-color, font-size, transform, color;
  transition-timing-function: ease-in-out;
}

.duration-1 {
  transition-duration: 0.5s;
}

.duration-2 {
  transition-duration: 2s;
}

.duration-3 {
  transition-duration: 4s;
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

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [CSS Transitions\
  [\#
  transition-duration-property]](https://drafts.csswg.org/css-transitions/#transition-duration-property)

  ----------------------------------------------------------------------------------------------------------------

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

`transition-duration`

261

1212

49164

1010

1512.110--15

93.1

4.42

2618

49164

1412.110.1--14

92

1.51.0

See also
--------

- [Using CSS transitions](using_css_transitions.md)
- [`transition`](transition.md)
- [`transition-property`](transition-property.md)
- [`transition-timing-function`](transition-timing-function.md)
- [`transition-delay`](transition-delay.md)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration>

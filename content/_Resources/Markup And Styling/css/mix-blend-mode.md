mix-blend-mode
==============

The `mix-blend-mode`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how an element\'s content should blend with the content of the
element\'s parent and the element\'s background.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
mix-blend-mode: normal;
mix-blend-mode: multiply;
mix-blend-mode: screen;
mix-blend-mode: overlay;
mix-blend-mode: darken;
mix-blend-mode: lighten;
mix-blend-mode: color-dodge;
mix-blend-mode: color-burn;
mix-blend-mode: hard-light;
mix-blend-mode: soft-light;
mix-blend-mode: difference;
mix-blend-mode: exclusion;
mix-blend-mode: hue;
mix-blend-mode: saturation;
mix-blend-mode: color;
mix-blend-mode: luminosity;

/* Global values */
mix-blend-mode: inherit;
mix-blend-mode: initial;
mix-blend-mode: revert;
mix-blend-mode: revert-layer;
mix-blend-mode: unset;
```

### Values

[`<blend-mode>`](blend-mode.md)

:   The blending mode that should be applied.

Formal definition
-----------------

  ------------------------------------------------------------------------------------------ ----------------
  [Initial value](initial_value.md)                                                             `normal`
  Applies to                                                                                 all elements
  [Inherited](inheritance.md)                                                                   no
  [Computed value](computed_value.md)                                                           as specified
  Animation type                                                                             Not animatable
  Creates [stacking context](stacking_context.md)   yes
  ------------------------------------------------------------------------------------------ ----------------

Formal syntax
-------------

```
mix-blend-mode = 
  <blend-mode>  |
  plus-darker   |
  plus-lighter  

<blend-mode> = 
  normal       |
  multiply     |
  screen       |
  overlay      |
  darken       |
  lighten      |
  color-dodge  |
  color-burn   |
  hard-light   |
  soft-light   |
  difference   |
  exclusion    |
  hue          |
  saturation   |
  color        |
  luminosity   
```

Examples
--------

### Effect of different mix-blend-mode values

### Using mix-blend-mode with HTML

#### HTML

[html]

```html
<div class="isolate">
  <div class="circle circle-1"></div>
  <div class="circle circle-2"></div>
  <div class="circle circle-3"></div>
</div>
```

#### CSS

[css]

```css
.circle {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  mix-blend-mode: screen;
  position: absolute;
}

.circle-1 {
  background: red;
}

.circle-2 {
  background: lightgreen;
  left: 40px;
}

.circle-3 {
  background: blue;
  left: 20px;
  top: 40px;
}

.isolate {
  isolation: isolate; /* Without isolation, the background color will be taken into account */
  position: relative;
}
```

#### Result

### Using mix-blend-mode with SVG

#### SVG

[html]

```html
<svg>
  <g class="isolate">
    <circle cx="40" cy="40" r="40" fill="red" />
    <circle cx="80" cy="40" r="40" fill="lightgreen" />
    <circle cx="60" cy="80" r="40" fill="blue" />
  </g>
</svg>
```

#### CSS

[css]

```css
circle {
  mix-blend-mode: screen;
}
.isolate {
  isolation: isolate;
} /* Without isolation, the background color will be taken into account */
```

#### Result

### Using mix-blend-mode with text

This example uses `mix-blend-mode` to blend text color with the
background color of its parent element.

#### HTML

[html]

```html
<div class="container">
  <p>Mostly Harmless</p>
  <p class="multiply">Mostly Harmless</p>
  <p class="screen">Mostly Harmless</p>
  <p class="hard-light">Mostly Harmless</p>
</div>
```

#### CSS

[css]

```css
@import url("https://fonts.googleapis.com/css2?family=Rubik+Moonrocks&display=swap");

.container {
  background-color: blue;
}

p {
  font:
    4rem "Rubik Moonrocks",
    cursive;
  font-weight: bold;
  color: orange;
  padding: 0.5rem;
  margin: 0;
}

.multiply {
  mix-blend-mode: multiply;
}

.screen {
  mix-blend-mode: screen;
}

.hard-light {
  mix-blend-mode: hard-light;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [Compositing and Blending Level 2\
  [\#
  mix-blend-mode]](https://drafts.fxtf.org/compositing/#mix-blend-mode)

  -------------------------------------------------------------------------------

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

`mix-blend-mode`

41

79

32

No

28

8

41

41

32

28

8

4.0

`plus-lighter`

100

100

99

No

No

9.1

100

100

99

No

9.3

19.0

`svg`

41

79

32

No

28

No

No

No

32

No

No

No

See also
--------

- [`<blend-mode>`](blend-mode.md)
- [`background-blend-mode`](background-blend-mode.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode>

background-blend-mode
=====================

The `background-blend-mode`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how an element\'s background images should blend with each other and
with the element\'s background color.

Try it
------

Blending modes should be defined in the same order as the
[`background-image`](background-image.md) property. If the blending modes\'
and background images\' list lengths are not equal, it will be repeated
and/or truncated until lengths match.

Syntax
------

[css]

```css
/* One value */
background-blend-mode: normal;

/* Two values, one per background */
background-blend-mode: darken, luminosity;

/* Global values */
background-blend-mode: inherit;
background-blend-mode: initial;
background-blend-mode: revert;
background-blend-mode: revert-layer;
background-blend-mode: unset;
```

### Values

[`<blend-mode>`](blend-mode.md)

:   The blending mode to be applied. There can be several values,
    separated by commas.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         All elements. In SVG, it applies to container elements, graphics elements, and graphics referencing elements.. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-blend-mode = 
  <mix-blend-mode>#  
```

Examples
--------

### Basic example

[css]

```css
.item {
  width: 300px;
  height: 300px;
  background: url("image1.png"), url("image2.png");
  background-blend-mode: screen;
}
```

### Try out different blend modes

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [Compositing and Blending Level 2\
  [\#
  background-blend-mode]](https://drafts.fxtf.org/compositing/#background-blend-mode)

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

`background-blend-mode`

35

79

30

No

22

8

37

35

30

22

8

3.0

See also
--------

- [`<blend-mode>`](blend-mode.md)
- [`mix-blend-mode`](mix-blend-mode.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-blend-mode>

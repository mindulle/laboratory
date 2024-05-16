mask-composite
==============

The `mask-composite`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
represents a compositing operation used on the current mask layer with
the mask layers below it.

Syntax
------

[css]

```css
/* Keyword values */
mask-composite: add;
mask-composite: subtract;
mask-composite: intersect;
mask-composite: exclude;

/* Global values */
mask-composite: inherit;
mask-composite: initial;
mask-composite: revert;
mask-composite: revert-layer;
mask-composite: unset;
```

One or more of the keyword values listed below, separated by commas.

### Values

For the composition the current mask layer is referred to as *source*,
while all layers below it are referred to as *destination*.

[`add`](#add)

:   The source is placed over the destination.

[`subtract`](#subtract)

:   The source is placed, where it falls outside of the destination.

[`intersect`](#intersect)

:   The parts of source that overlap the destination, replace the
    destination.

[`exclude`](#exclude)

:   The non-overlapping regions of source and destination are combined.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `add`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-composite = 
  <compositing-operator>#  

<compositing-operator> = 
  add        |
  subtract   |
  intersect  |
  exclude    
```

Examples
--------

### Compositing mask layers with addition

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-composite]](https://drafts.fxtf.org/css-masking/#the-mask-composite)

  ---------------------------------------------------------------------------------------

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

`mask-composite`

NoSee also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

18--79

53

No

NoSee also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

15.4See also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

NoSee also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

NoSee also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

53

NoSee also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

15.4See also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

NoSee also
[`-webkit-mask-composite`](https://developer.mozilla.org/docs/Web/CSS/-webkit-mask-composite)
for a similar non-standard property that uses different keywords.

See also
--------

- [Clipping and Masking in
    CSS](https://css-tricks.com/clipping-masking-css/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-composite>

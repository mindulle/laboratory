mask-position
=============

The `mask-position`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the initial position, relative to the mask position layer set by
[`mask-origin`](mask-origin.md), for each defined mask image.

Syntax
------

[css]

```css
/* Keyword values */
mask-position: top;
mask-position: bottom;
mask-position: left;
mask-position: right;
mask-position: center;

/* <position> values */
mask-position: 25% 75%;
mask-position: 0px 0px;
mask-position: 10% 8em;

/* Multiple values */
mask-position: top right;
mask-position:
  1rem 1rem,
  center;

/* Global values */
mask-position: inherit;
mask-position: initial;
mask-position: revert;
mask-position: revert-layer;
mask-position: unset;
```

One or more `<position>` values, separated by commas.

### Values

[`<position>`](position_value.md)

:   One to four values representing a 2D position regarding the edges of
    the element\'s box. Relative or absolute offsets can be given. Note
    that the position can be set outside of the element\'s box.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `center`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to size of mask painting area minus size of mask layer image (see the text for [`background-position`](background-position.md))
  [Computed value](computed_value.md)   Consists of two keywords representing the origin and two offsets from that origin, each given as an absolute length (if given a \<length\>), otherwise as a percentage.
  Animation type                     a repeatable list
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-position = 
  <position>#  

<position> = 
  [ left | center | right ] || [ top | center | bottom ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]?  |
  [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ]  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting mask position

Change the `mask-position` value to any of the allowed values detailed
above. If viewing the example in a Chromium-based browser change the
value of `-webkit-mask-position`.

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-position]](https://drafts.fxtf.org/css-masking/#the-mask-position)

  -------------------------------------------------------------------------------------

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

`mask-position`

1

7918--79

53

No

15

15.43.1

2

18

53

14

15.42

1.0

See also
--------

- [Clipping and Masking in
    CSS](https://css-tricks.com/clipping-masking-css/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-position>

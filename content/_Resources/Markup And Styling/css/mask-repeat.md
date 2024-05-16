mask-repeat
===========

The `mask-repeat`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
how mask images are repeated. A mask image can be repeated along the
horizontal axis, the vertical axis, both axes, or not repeated at all.

By default, the repeated images are clipped to the size of the element,
but they can be scaled to fit (using `round`) or evenly distributed from
end to end (using `space`).

Syntax
------

[css]

```css
/* One-value syntax */
mask-repeat: repeat-x;
mask-repeat: repeat-y;
mask-repeat: repeat;
mask-repeat: space;
mask-repeat: round;
mask-repeat: no-repeat;

/* Two-value syntax: horizontal | vertical */
mask-repeat: repeat space;
mask-repeat: repeat repeat;
mask-repeat: round space;
mask-repeat: no-repeat round;

/* Multiple values */
mask-repeat:
  space round,
  no-repeat;
mask-repeat:
  round repeat,
  space,
  repeat-x;

/* Global values */
mask-repeat: inherit;
mask-repeat: initial;
mask-repeat: revert;
mask-repeat: revert-layer;
mask-repeat: unset;
```

One or more `<repeat-style>` values, separated by commas.

### Values

[`<repeat-style>`](#repeat-style)

:   The one-value syntax is a shorthand for the full two-value syntax:

      Single value   Two-value equivalent
      -------------- -----------------------
      `repeat-x`     `repeat no-repeat`
      `repeat-y`     `no-repeat repeat`
      `repeat`       `repeat repeat`
      `space`        `space space`
      `round`        `round round`
      `no-repeat`    `no-repeat no-repeat`
    

    In the two-value syntax, the first value represents the horizontal
    repetition behavior and the second value represents the vertical
    behavior. Here is an explanation of how each option works for either
    direction:

    
      ------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
      `repeat`      The image is repeated as much as needed to cover the whole mask painting area. The last image will be clipped if it doesn\'t fit.
      `space`       The image is repeated as much as possible without clipping. The first and last images are pinned to either side of the element, and whitespace is distributed evenly between the images. The [`mask-position`](mask-position) property is ignored unless only one image can be displayed without clipping. The only case where clipping happens using `space` is when there isn\'t enough room to display one image.
      `round`       As the allowed space increases in size, the repeated images will stretch (leaving no gaps) until there is room for another one to be added. When the next image is added, all of the current ones compress to allow room. Example: An image with an original width of 260px, repeated three times, might stretch until each repetition is 300px wide, and then another image will be added. They will then compress to 225px.
      `no-repeat`   The image is not repeated (and hence the mask painting area will not necessarily be entirely covered). The position of the non-repeated mask image is defined by the [`mask-position`](mask-position) CSS property.
      ------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `repeat`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   Consists of two keywords, one per dimension
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-repeat = 
  <repeat-style>#  

<repeat-style> = 
  repeat-x                                     |
  repeat-y                                     |
  [ repeat | space | round | no-repeat ]  
```

Examples
--------

### Setting repeat for a single mask

### Multiple mask image support

You can specify a different `<repeat-style>` for each mask image,
separated by commas:

[css]

```css
.examplethree {
  mask-image: url("mask1.png"), url("mask2.png");
  mask-repeat: repeat-x, repeat-y;
}
```

Each image is matched with the corresponding repeat style, from first
specified to last.

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-repeat]](https://drafts.fxtf.org/css-masking/#the-mask-repeat)

  ---------------------------------------------------------------------------------

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

`mask-repeat`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-repeat>

border-image-repeat
===================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `border-image-repeat`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
how the [edge regions](border-image-slice.md#edge-regions) and [](border-image-slice.md#middle-region) of a source image are adjusted
to fit the dimensions of an element\'s [border image](border-image.md). The
middle region can be displayed by using the keyword \"fill\" in the
border-image-slice property.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
border-image-repeat: stretch;
border-image-repeat: repeat;
border-image-repeat: round;
border-image-repeat: space;

/* top and bottom | left and right */
border-image-repeat: round stretch;

/* Global values */
border-image-repeat: inherit;
border-image-repeat: initial;
border-image-repeat: revert;
border-image-repeat: revert-layer;
border-image-repeat: unset;
```

The `border-image-repeat` property may be specified using one or two
values chosen from the list of values below.

- When **one** value is specified, it applies the same behavior on
    **all four sides**.
- When **two** values are specified, the first applies to the **top,
    middle, and bottom**, the second to the **left and right**.

### Values

[`stretch`](#stretch)

:   The source image\'s edge regions are stretched to fill the gap
    between each border.

[`repeat`](#repeat)

:   The source image\'s edge regions are tiled (repeated) to fill the
    gap between each border. Tiles may be clipped to achieve the proper
    fit.

[`round`](#round)

:   The source image\'s edge regions are tiled (repeated) to fill the
    gap between each border. Tiles may be stretched to achieve the
    proper fit.

[`space`](#space)

:   The source image\'s edge regions are tiled (repeated) to fill the
    gap between each border. Extra space will be distributed in between
    tiles to achieve the proper fit.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `stretch`
  Applies to                         all elements, except internal table elements when [`border-collapse`](border-collapse.md) is `collapse`. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-image-repeat = 
  [ stretch | repeat | round | space ]  
```

Examples
--------

### Repeating border images

#### CSS

[css]

```css
#bordered {
  width: 12rem;
  margin-bottom: 1rem;
  padding: 1rem;
  border: 40px solid;
  border-image: url("border.png") 27;
  border-image-repeat: stretch; /* Can be changed in the live sample */
}
```

#### Results

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-image-repeat]](https://drafts.csswg.org/css-backgrounds/#the-border-image-repeat)

  ------------------------------------------------------------------------------------------------------

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

`border-image-repeat`

15

12

15

11

15

6

4.4

18

15

14

9.3

1.0

`round`

30

12

15

11

17

9.1

≤37

30

15

18

9.3

2.0

`space`

56

12

50

11

43

9.1

56

56

50

43

9.3

6.0

See also
--------

- [Backgrounds and borders](css_backgrounds_and_borders.md)
- [Learn CSS: Backgrounds and
    borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-repeat>

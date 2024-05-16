perspective-origin
==================

The `perspective-origin`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
determines the position at which the viewer is looking. It is used as
the *vanishing point* by the [`perspective`](_Resources/Markup%20And%20Styling/css/perspective.md) property.

Try it
------

The `perspective-origin` and [`perspective`](_Resources/Markup%20And%20Styling/css/perspective.md) properties are
attached to the parent of a child transformed in 3-dimensional space,
unlike the [`perspective()`](_Resources/Markup%20And%20Styling/css/transform-function/perspective.md) transform
function which is placed on the element being transformed.

Syntax
------

[css]

```css
/* One-value syntax */
perspective-origin: x-position;

/* Two-value syntax */
perspective-origin: x-position y-position;

/* When both x-position and y-position are keywords,
   the following is also valid */
perspective-origin: y-position x-position;

/* Global values */
perspective-origin: inherit;
perspective-origin: initial;
perspective-origin: revert;
perspective-origin: revert-layer;
perspective-origin: unset;
```

### Values

[*x-position*](#x-position)

:   Indicates the position of the abscissa of the *vanishing point*. It
    can have one of the following values:

    -   [`<length-percentage>`](length-percentage) indicating the
        position as an absolute length value or relative to the width of
        the element. The value may be negative.
    -   `left`, a keyword being a shortcut for the `0` length value.
    -   `center`, a keyword being a shortcut for the `50%` percentage
        value.
    -   `right`, a keyword being a shortcut for the `100%` percentage
        value.

[*y-position*](#y-position)

:   Indicates the position of the ordinate of the *vanishing point*. It
    can have one of the following values:

    -   [`<length-percentage>`](length-percentage) indicating the
        position as an absolute length value or relative to the height
        of the element. The value may be negative.
    -   `top`, a keyword being a shortcut for the `0` length value.
    -   `center`, a keyword being a shortcut for the `50%` percentage
        value.
    -   `bottom`, a keyword being a shortcut for the `100%` percentage
        value.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------
  [Initial value](initial_value.md)     `50% 50%`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to the size of bounding box
  [Computed value](computed_value.md)   for [`<length>`](length.md) the absolute value, otherwise a percentage
  Animation type                     simple list of length, percentage, or calc
  ---------------------------------- ---------------------------------------------------------------------

Formal syntax
-------------

```
perspective-origin = 
  <position>  

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

### Changing the perspective origin

An example showing how to change `perspective-origin` is given in [](using_css_transforms.md#changing_the_perspective_origin).

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  perspective-origin-property]](https://drafts.csswg.org/css-transforms-2/#perspective-origin-property)

  ---------------------------------------------------------------------------------------------------------------

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

`perspective-origin`

3612

1212

491610

10

2315

94

4.43

3618

491610

2414

92

3.01.0

See also
--------

- [Using CSS Transforms](using_css_transforms.md)
- [`transform-style`](transform-style.md)
- [`<transform-function>`](transform-function.md)
- [`perspective`](_Resources/Markup%20And%20Styling/css/perspective.md)
- [`transform: perspective()`](_Resources/Markup%20And%20Styling/css/transform-function/perspective.md)
    function

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/perspective-origin>

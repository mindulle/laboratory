perspective
===========

The `perspective`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
determines the distance between the z=0 plane and the user in order to
give a 3D-positioned element some perspective.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
perspective: none;

/* <length> values */
perspective: 20px;
perspective: 3.5em;

/* Global values */
perspective: inherit;
perspective: initial;
perspective: revert;
perspective: revert-layer;
perspective: unset;
```

### Values

[`none`](#none)

:   Indicates that no perspective transform is to be applied.

[`<length>`](#length)

:   A [`<length>`](length.md) giving the distance from the user to the z=0
    plane. It is used to apply a perspective transform to the children
    of the element. Negative values are syntax errors. If the value is
    smaller than `1px`, it is clamped to `1px`.

Description
-----------

Each 3D element with z\>0 becomes larger; each 3D-element with z\<0
becomes smaller. The strength of the effect is determined by the value
of this property. Large values of `perspective` cause a small
transformation; small values of `perspective` cause a large
transformation.

The parts of the 3D elements that are behind the user --- i.e. their
z-axis coordinates are greater than the value of the `perspective` CSS
property --- are not drawn.

The *vanishing point* is by default placed at the center of the element,
but its position can be changed using the
[`perspective-origin`](perspective-origin.md) property.

Using this property with a value other than `none` creates a new
[](stacking_context.md).
Also, in that case, the object will act as a containing block for
`position: fixed` elements that it contains.

Formal definition
-----------------

  ------------------------------------------------------------------------------------------ ----------------------------------
  [Initial value](initial_value.md)                                                             `none`
  Applies to                                                                                 transformable elements
  [Inherited](inheritance.md)                                                                   no
  [Computed value](computed_value.md)                                                           the absolute length or `none`
  Animation type                                                                             a [length](length.md#interpolation)
  Creates [stacking context](stacking_context.md)   yes
  ------------------------------------------------------------------------------------------ ----------------------------------

Formal syntax
-------------

```
perspective = 
  none            |
  <length [0,∞]>  
```

Examples
--------

### Setting perspective

An example showing how a cube varies if the `perspective` is set at
different positions is given in [](using_css_transforms.md#setting_perspective).

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  perspective-property]](https://drafts.csswg.org/css-transforms-2/#perspective-property)

  -------------------------------------------------------------------------------------------------

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

`perspective`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/perspective>

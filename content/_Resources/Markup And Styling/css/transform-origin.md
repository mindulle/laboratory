transform-origin
================

The `transform-origin`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the origin for an element\'s transformations.

Try it
------

The transform origin is the point around which a transformation is
applied. For example, the transform origin of the
[`rotate()`](_Resources/Markup%20And%20Styling/css/transform-function/rotate.md) function is the center of
rotation.

In effect, this property wraps a pair of translations around the
element\'s other transformations. The first translation moves the
transform origin to the true origin at $(0,0)$. Then the other
transformations are applied, and because the transform origin is at
$(0,0)$, those transformations act about the transform origin. Finally,
the opposite translation is applied, moving the transform origin back to
its original location. Consequently, this definition

[css]

```css
transform-origin: -100% 50%;
transform: rotate(45deg);
```

results in the same transformation as

[css]

```css
transform-origin: 0 0;
transform: translate(-100%, 50%) rotate(45deg) translate(100%, -50%);
```

Reading from right to left, `translate(100%, -50%)` is the translation
to bring the transform origin to the true origin, `rotate(45deg)` is the
original transformation, and `translate(-100%, 50%)` is the translation
to restore the transform origin to its original location.

By default, the origin of a transform is `center`.

Syntax
------

[css]

```css
/* One-value syntax */
transform-origin: 2px;
transform-origin: bottom;

/* x-offset | y-offset */
transform-origin: 3cm 2px;

/* x-offset-keyword | y-offset */
transform-origin: left 2px;

/* x-offset-keyword | y-offset-keyword */
transform-origin: right top;

/* y-offset-keyword | x-offset-keyword */
transform-origin: top right;

/* x-offset | y-offset | z-offset */
transform-origin: 2px 30% 10px;

/* x-offset-keyword | y-offset | z-offset */
transform-origin: left 5px -3px;

/* x-offset-keyword | y-offset-keyword | z-offset */
transform-origin: right bottom 2cm;

/* y-offset-keyword | x-offset-keyword | z-offset */
transform-origin: bottom right 2cm;

/* Global values */
transform-origin: inherit;
transform-origin: initial;
transform-origin: revert;
transform-origin: revert-layer;
transform-origin: unset;
```

The `transform-origin` property may be specified using one, two, or
three values, where each value represents an offset. Offsets that are
not explicitly defined are reset to their corresponding [](initial_value.md).

If a single [`<length>`](length.md) or [`<percentage>`](percentage.md) value
is defined, it represents the horizontal offset.

If two or more values are defined and either no value is a keyword, or
the only used keyword is `center`, then the first value represents the
horizontal offset and the second represents the vertical offset.

- One-value syntax:
  - The value must be a [`<length>`](length.md), a
        [`<percentage>`](percentage.md), or one of the keywords `left`,
        `center`, `right`, `top`, and `bottom`.
- Two-value syntax:
  - One value must be a [`<length>`](length.md), a
        [`<percentage>`](percentage.md), or one of the keywords `left`,
        `center`, and `right`.
  - The other value must be a [`<length>`](length.md), a
        [`<percentage>`](percentage.md), or one of the keywords `top`,
        `center`, and `bottom`.
- Three-value syntax:
  - The first two values are the same as for the two-value syntax.
  - The third value must be a [`<length>`](length.md). It always
        represents the Z offset.

### Values

[*x-offset*](#x-offset)

:   Is a [`<length>`](length.md) or a [`<percentage>`](percentage.md)
    describing how far from the left edge of the box the origin of the
    transform is set.

[*offset-keyword*](#offset-keyword)

:   Is one of the `left`, `right`, `top`, `bottom`, or `center` keyword
    describing the corresponding offset.

[*y-offset*](#y-offset)

:   Is a [`<length>`](length.md) or a [`<percentage>`](percentage.md)
    describing how far from the top edge of the box the origin of the
    transform is set.

[*x-offset-keyword*](#x-offset-keyword)

:   Is one of the `left`, `right`, or `center` keyword describing how
    far from the left edge of the box the origin of the transform is
    set.

[*y-offset-keyword*](#y-offset-keyword)

:   Is one of the `top`, `bottom`, or `center` keyword describing how
    far from the top edge of the box the origin of the transform is set.

[*z-offset*](#z-offset)

:   Is a [`<length>`](length.md) (and never a [`<percentage>`](percentage.md)
    which would make the statement invalid) describing how far from the
    user eye the z=0 origin is set.

The keywords are convenience shorthands and match the following
[`<percentage>`](percentage.md) values:

  Keyword    Value
  ---------- --------
  `left`     `0%`
  `center`   `50%`
  `right`    `100%`
  `top`      `0%`
  `bottom`   `100%`

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------
  [Initial value](initial_value.md)     `50% 50% 0`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to the size of bounding box
  [Computed value](computed_value.md)   for [`<length>`](length.md) the absolute value, otherwise a percentage
  Animation type                     simple list of length, percentage, or calc
  ---------------------------------- ---------------------------------------------------------------------

**Note:** The initial value of `transform-origin` is `0 0` for all SVG
elements except for root `<svg>` elements and `<svg>` elements that are
a direct child of a
[foreignObject](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/foreignObject),
and whose `transform-origin` is `50% 50%`, like other CSS elements. See
the [SVG
transform-origin](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/transform-origin)
attribute for more information.

Formal syntax
-------------

```
transform-origin = 
  [ left | center | right | top | bottom | <length-percentage> ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ] <length>?  |
  [ [ center | left | right ] && [ center | top | bottom ] ] <length>?  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### A demonstration of various transform values

This example shows the effect of choosing different `transform-origin`
values for a variety of transformation functions.

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 1\
  [\#
  transform-origin-property]](https://drafts.csswg.org/css-transforms/#transform-origin-property)

  ---------------------------------------------------------------------------------------------------------

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

`transform-origin`

361

1212

49163.5

109

231512.1--1510.5--15

92

≤374.4

3618

49164

241512.1--1511--14

91

3.01.0

`support_in_svg`

19

17

43Keywords and percentages refer to the canvas instead of the object
itself. See [bug 1209061](https://bugzil.la/1209061).

No

15

6Only supported for transformations applied using the CSS `transform`
property (e.g.
`.className`).
It has no effect on transformations applied using the `transform` SVG
attribute (e.g.
`<rect style="transform-origin: center;" transform="rotate(45)" />`).

4.4

25

43Keywords and percentages refer to the canvas instead of the object
itself. See [bug 1209061](https://bugzil.la/1209061).

14

6Only supported for transformations applied using the CSS `transform`
property (e.g.
`.className`).
It has no effect on transformations applied using the `transform` SVG
attribute (e.g.
`<rect style="transform-origin: center;" transform="rotate(45)" />`).

1.5

`three_value_syntax`

12

12

10

9

15

5

≤37

18

10

14

3.2

1.0

See also
--------

- [Using CSS transforms](using_css_transforms.md)
- https://css-tricks.com/almanac/properties/t/transform-origin/>

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin>

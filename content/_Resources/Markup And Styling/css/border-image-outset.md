border-image-outset
===================

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `border-image-outset`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the distance by which an element\'s [border image](border-image.md) is set
out from its border box.

The parts of the border image that are rendered outside the element\'s
border box with `border-image-outset` do not trigger overflow scrollbars
and don\'t capture mouse events.

Try it
------

Syntax
------

[css]

```css
/* <length> value */
border-image-outset: 1rem;

/* <number> value */
border-image-outset: 1.5;

/* top and bottom | left and right */
border-image-outset: 1 1.2;

/* top | left and right | bottom */
border-image-outset: 30px 2 45px;

/* top | right | bottom | left */
border-image-outset: 7px 12px 14px 5px;

/* Global values */
border-image-outset: inherit;
border-image-outset: initial;
border-image-outset: revert;
border-image-outset: revert-layer;
border-image-outset: unset;
```

The `border-image-outset` property may be specified as one, two, three,
or four values. Each value is a [`<length>`](length.md) or
[`<number>`](number.md). Negative values are invalid and will cause the
`border-image-outset` declaration to be ignored.

1. If **one** value is specified, it applies to **all four sides**.
2. If **two** values are specified, the first applies to the **top and
    bottom** and the second to the **left and right**.
3. If **three** values are specified, the first applies to the **top**,
    the second to the **left and right**, and the third to the
    **bottom**.
4. If **four** values are specified, they apply to the **top**,
    **right**, **bottom**, and **left** in that order (clockwise).

### Values

[`<length>`](length.md)

:   The size of the `border-image` outset as a dimension --- a number
    with a unit.

[`<number>`](number.md)

:   The size of the `border-image` outset as a multiple of the
    element\'s corresponding [`border-width`](border-width.md)s. For
    example, if an element has `border-width: 1em 2px 0 1.5rem`, and
    `border-image-outset: 2`, the final `border-image-outset` would be
    calculated as `2em 4px 0 3rem`.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements, except internal table elements when [`border-collapse`](border-collapse.md) is `collapse`. It also applies to [`::first-letter`](::first-letter).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  Animation type                     by computed value type
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
border-image-outset = 
  [ <length [0,∞]> | <number [0,∞]> ]  
```

Examples
--------

### Outsetting a border image

#### HTML

[html]

```html
<div id="outset">This element has an outset border image!</div>
```

#### CSS

[css]

```css
#outset {
  width: 10rem;
  background: #cef;
  border: 1.4rem solid;
  border-image: radial-gradient(#ff2, #55f) 40;
  border-image-outset: 1.5; /* 1.5 × 1.4rem = 2.1rem */
  margin: 2.1rem;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  the-border-image-outset]](https://drafts.csswg.org/css-backgrounds/#the-border-image-outset)

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

`border-image-outset`

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

6

1.0

See also
--------

- [Backgrounds and borders](css_backgrounds_and_borders.md)
- [Learn CSS: Backgrounds and
    borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/border-image-outset>

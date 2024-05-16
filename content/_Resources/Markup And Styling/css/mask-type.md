mask-type
=========

The `mask-type` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether an SVG
[`<mask>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask)
element is used as a *luminance* or an *alpha* mask. It applies to the
`<mask>` element itself.

This property may be overridden by the [`mask-mode`](mask-mode.md)
property, which has the same effect but applies to the element where the
mask is used. Alpha masks will generally be faster to render.

Syntax
------

[css]

```css
/* Keyword values */
mask-type: luminance;
mask-type: alpha;

/* Global values */
mask-type: inherit;
mask-type: initial;
mask-type: revert;
mask-type: revert-layer;
mask-type: unset;
```

The `mask-type` property is specified as one of the keyword values
listed below.

### Values

[`luminance`](#luminance)

:   Is a keyword indicating that the associated mask image is a
    luminance mask, i.e., that its [relative
    luminance](https://en.wikipedia.org/wiki/Luminance_%28relative%29)
    values must be used when applying it.

[`alpha`](#alpha)

:   Is a keyword indicating that the associated mask image is an alpha
    mask, i.e., that its [alpha
    channel](https://en.wikipedia.org/wiki/Alpha_compositing) values
    must be used when applying it.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `luminance`
  Applies to                         [`<mask>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/mask) elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------------------------------------------------------------------

Formal syntax
-------------

```
mask-type = 
  luminance  |
  alpha      
```

Examples
--------

### Setting an alpha mask

#### HTML

[html]

```html
<div class="redsquare"></div>
<svg
  version="1.1"
  xmlns="http://www.w3.org/2000/svg"
  xmlns:xlink="http://www.w3.org/1999/xlink"
  width="0"
  height="0">
  <defs>
    <mask id="m" maskContentUnits="objectBoundingBox" style="mask-type:alpha">
      <rect
        x=".1"
        y=".1"
        width=".8"
        height=".8"
        fill="red"
        fill-opacity="0.7" />
    </mask>
  </defs>
</svg>
```

#### CSS

[css]

```css
.redsquare {
  height: 100px;
  width: 100px;
  background-color: rgb(128, 128, 128);
  border: solid 1px black;
  mask: url("#m");
}
```

#### Result

### Setting a luminance mask

#### HTML

[html]

```html
<div class="redsquare"></div>
<svg
  version="1.1"
  xmlns="http://www.w3.org/2000/svg"
  xmlns:xlink="http://www.w3.org/1999/xlink"
  width="0"
  height="0">
  <defs>
    <mask
      id="m"
      maskContentUnits="objectBoundingBox"
      style="mask-type:luminance">
      <rect
        x=".1"
        y=".1"
        width=".8"
        height=".8"
        fill="red"
        fill-opacity="0.7" />
    </mask>
  </defs>
</svg>
```

#### CSS

[css]

```css
.redsquare {
  height: 100px;
  width: 100px;
  background-color: rgb(128, 128, 128);
  border: solid 1px black;
  mask: url("#m");
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\#
  the-mask-type]](https://drafts.fxtf.org/css-masking/#the-mask-type)

  -----------------------------------------------------------------------------

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

`mask-type`

24

79

35

No

15

7

37

25

35

14

7

1.5

See also
--------

- Other mask-related properties: [`mask`](mask.md),
    [`mask-mode`](mask-mode.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/mask-type>

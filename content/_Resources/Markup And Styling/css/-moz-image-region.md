-moz-image-region
=================

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

For certain XUL elements and pseudo-elements that use an image from the
[`list-style-image`](list-style-image.md) property, this property specifies
a region of the image that is used in place of the whole image. This
allows elements to use different pieces of the same image to improve
performance.

The syntax is similar to the [`clip`](clip.md) property. All four values
are relative to the upper left corner of the image.

**Note:** For a system that works on any background, see
[`-moz-image-rect()`](-moz-image-rect.md).

Syntax
------

[css]

```css
/* Keyword value */
-moz-image-region: auto;

/* <shape> value */
-moz-image-region: rect(0, 8px, 4px, 4px);

/* Global values */
-moz-image-region: inherit;
-moz-image-region: initial;
-moz-image-region: unset;
```

### Values

[`auto`](#auto)

:   Automatically defines the region of the image to use.

[`<shape>`](shape.md)

:   A shape defining the part of the image to use. The `rect()` function
    defines a rectangle to use as shape. Its parameters define the top,
    right, bottom, and left offsets of the edges of the image, in this
    order.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         XUL [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) elements and [`:-moz-tree-image`](:-moz-tree-image) pseudo-elements. **Note:** `-moz-image-region` only works with [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) elements where the icon is specified using [`list-style-image`](list-style-image.md). It will not work with XUL `<image src="url" />`.
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
 -moz-image-region =
   <shape> | auto
```

Examples
--------

### Clipping an image

[css]

```css
#example-button {
  /* display only the 4x4 area from the top left of this image */
  list-style-image: url("chrome://example/skin/example.png");
  -moz-image-region: rect(0px, 4px, 4px, 0px);
}
#example-button:hover {
  /* use the 4x4 area to the right of the first for the hovered button */
  -moz-image-region: rect(0px, 8px, 4px, 4px);
}
```

Specifications
--------------

Not part of any standard.

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

`-moz-image-region`

No

No

1--112

No

No

No

No

No

4--112

No

No

No

See also
--------

- [`-moz-image-rect()`](-moz-image-rect.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/-moz-image-region>

image-orientation
=================

The `image-orientation`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies a layout-independent correction to the orientation of an
image.

Try it
------

Syntax
------

[css]

```css
/* keyword values */
image-orientation: none;
image-orientation: from-image; /* Use EXIF data from the image */

/* Global values */
image-orientation: inherit;
image-orientation: initial;
image-orientation: revert;
image-orientation: revert-layer;
image-orientation: unset;
```

### Values

[`none`](#none)

:   Does not apply any additional image rotation; the image is oriented
    as encoded or as other CSS property values dictate.

[`from-image`](#from-image)

:   Default initial value. The
    [EXIF](https://en.wikipedia.org/wiki/EXIF) information contained in
    the image is used to rotate the image appropriately.

**Warning:** `image-orientation: none;` **does not** override the
orientation of non-secure-origin images as encoded by their
[EXIF](https://en.wikipedia.org/wiki/EXIF) information, due to security
concerns. Find out more from [the CSS working group draft
issue](https://github.com/w3c/csswg-drafts/issues/5165).

Description
-----------

This property is intended *only* to be used for the purpose of
correcting the orientation of images which were shot with the camera
rotated. It should *not* be used for arbitrary rotations. For any
purpose other than correcting an image\'s orientation due to how it was
shot or scanned, use a [`transform`](transform.md) property with the
`rotate` keyword to specify rotation. This includes any user-directed
changes to the orientation of the image, or changes required for
printing in portrait versus landscape orientation.

If used in conjunction with other CSS properties, such as a
[`<transform-function>`](transform-function.md), any `image-orientation`
rotation is applied before any other transformations.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `from-image`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   an [`<angle>`](angle.md), rounded to the next quarter turn from `0deg` and normalized, that is moduloing the value by `1turn`
  Animation type                     discrete
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
image-orientation = 
  from-image           |
  none                 |
  [ <angle> || flip ]  
```

Examples
--------

### Orienting image from image data

The following image has been rotated through 180 degrees, and the
`image-orientation` property is used to correct its orientation based on
the EXIF data in the image. By changing the `image-orientation` to
`none` you can see the effect of the property.

#### CSS

[css]

```css
#image {
  image-orientation: from-image; /* Can be changed in the live sample */
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Images Module Level 3\
  [\#
  the-image-orientation]](https://drafts.csswg.org/css-images/#the-image-orientation)

  ---------------------------------------------------------------------------------------------

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

`image-orientation`

81

81

26

No

67

13.1

81

81

26

58

13.4

13.0

`flip_and_angle`

No

No

26--63

No

No

No

No

No

26--63

No

No

No

See also
--------

- Other image-related CSS properties: [`object-fit`](object-fit.md),
    [`object-position`](object-position.md),
    [`image-orientation`](image-orientation.md),
    [`image-rendering`](image-rendering.md),
    [`image-resolution`](image-resolution.md).
- [`transform`](transform.md) and [`rotate`](_Resources/Markup%20And%20Styling/css/rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/image-orientation>

image-rendering
===============

The `image-rendering`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets an
image scaling algorithm. The property applies to an element itself, to
any images set in its other properties, and to its descendants.

Try it
------

The [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
will scale an image when the page author specifies dimensions other than
its natural size. Scaling may also occur due to user interaction
(zooming). For example, if the natural size of an image is
`100×100px`*,* but its actual dimensions are `200×200px` (or `50×50px`),
then the image will be upscaled (or downscaled) using the algorithm
specified by `image-rendering`. This property has no effect on
non-scaled images.

Syntax
------

[css]

```css
/* Keyword values */
image-rendering: auto;
image-rendering: crisp-edges;
image-rendering: pixelated;

/* Global values */
image-rendering: inherit;
image-rendering: initial;
image-rendering: revert;
image-rendering: revert-layer;
image-rendering: unset;
```

### Values

[`auto`](#auto)

:   The scaling algorithm is UA dependent. Since version 1.9 (Firefox
    3.0), Gecko uses *bilinear* resampling (high quality).

[`smooth`](#smooth) [Experimental]

:   The image should be scaled with an algorithm that maximizes the
    appearance of the image. In particular, scaling algorithms that
    \"smooth\" colors are acceptable, such as bilinear interpolation.
    This is intended for images such as photos.

[`high-quality`](#high-quality) [Experimental]

:   Identical to `smooth`, but with a preference for higher-quality
    scaling. If system resources are constrained, images with
    `high-quality` should be prioritized over those with any other
    value, when considering which images to degrade the quality of and
    to what degree.

[`crisp-edges`](#crisp-edges)

:   The image is scaled with an algorithm that preserves contrast and
    edges in the image. Generally intended for images such as pixel art
    or line drawings, no blurring or color smoothing occurs.

[`pixelated`](#pixelated)

:   The image is scaled with the \"nearest neighbor\" or similar
    algorithm, preserving a \"pixelated\" look as the image changes in
    size.

**Note:** The values `optimizeQuality` and `optimizeSpeed` present in an
early draft (and coming from its SVG counterpart `image-rendering`) are
defined as synonyms for the `smooth` and `pixelated` values
respectively.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
image-rendering = 
  auto          |
  smooth        |
  high-quality  |
  pixelated     |
  crisp-edges   
```

Examples
--------

### Setting image scaling algorithms

In practical use, the `pixelated` and `crisp-edges` rules can be
combined to provide some fallback for each other. (Just prepend the
actual rules with the fallback.) The [Canvas
API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API) can
provide a [fallback solution for
`pixelated`](http://phrogz.net/tmp/canvas_image_zoom.html) through
manual image data manipulation or with
[`imageSmoothingEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/imageSmoothingEnabled).

#### CSS

[css]

```css
.auto {
  image-rendering: auto;
}

.pixelated {
  image-rendering: pixelated;
}

.crisp-edges {
  image-rendering: -webkit-optimize-contrast;
  image-rendering: crisp-edges;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Images Module Level 3\
  [\#
  the-image-rendering]](https://drafts.csswg.org/css-images/#the-image-rendering)

  -----------------------------------------------------------------------------------------

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

`image-rendering`

13

79

3.6

No

15

6

3

18

4

14

6

1.0

`crisp-edges`

13

79

653.6

No

15

76

≤37

18

654

14

76

1.0

`optimizeQuality`

No

No

3.6

No

No

7

No

No

4

No

7

No

`optimizeSpeed`

No

No

3.6

No

No

7

No

No

4

No

7

No

`pixelated`

41

79

93

No

26

10

41

41

93

26

10

4.0

**Note:** Although `crisp-edges` is supposed to use a pixel-art scaler
like in the specification example, in practice no browsers (as of
January 2020) do so. [In
Firefox](https://searchfox.org/mozilla-central/rev/1061fae5e225a99ef5e43dbdf560a91a0c0d00d1/gfx/wr/webrender/src/resource_cache.rs#1356),
`crisp-edges` or `pixelated` is interpreted as nearest-neighbor, and
`auto` is interpolated as trilinear or linear.

For behavior on Chromium and Safari (WebKit), see the
[`GetInterpolationQuality`](https://source.chromium.org/chromium/chromium/src/+/main:third_party/blink/renderer/core/style/computed_style.cc;l=1160)
function and
[`CSSPrimitiveValue::operator ImageRendering()`](https://github.com/WebKit/WebKit/blob/9b26fc6081e0db8a1304cf4b4f8f1c67efb9bc0c/Source/WebCore/css/CSSPrimitiveValueMappings.h#L4045)
respectively.

See also
--------

- Other image-related CSS properties: [`object-fit`](object-fit.md),
    [`object-position`](object-position.md),
    [`image-orientation`](image-orientation.md),
    [`image-rendering`](image-rendering.md),
    [`image-resolution`](image-resolution.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/image-rendering>

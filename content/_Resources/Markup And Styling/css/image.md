\<image\>
=========

The `<image>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents a two-dimensional image.

Syntax
------

The `<image>` data type can be represented with any of the following:

- An image denoted by the [`url()`](url.md) data type
- A [`<gradient>`](gradient.md) data type
- A part of the webpage, defined by the [`element()`](element().md)
    function
- An image, image fragment or solid patch of color, defined by the
    [`image()`](_Resources/Markup%20And%20Styling/css/image/image.md) function
- A blending of two or more images defined by the
    [`cross-fade()`](cross-fade.md) function.
- A selection of images chosen based on resolution defined by the
    [`image-set()`](image-set.md) function.

Description
-----------

CSS can handle the following kinds of images:

- Images with *intrinsic dimensions* (a natural size), like a JPEG,
    PNG, or other [raster
    format](https://en.wikipedia.org/wiki/Raster_graphics).
- Images with *multiple intrinsic dimensions*, existing in multiple
    versions inside a single file, like some .ico formats. (In this
    case, the intrinsic dimensions will be those of the image largest in
    area and the aspect ratio most similar to the containing box.)
- Images with no intrinsic dimensions but with *an intrinsic aspect
    ratio* between its width and height, like an SVG or other [vector
    format](https://en.wikipedia.org/wiki/Vector_graphics).
- Images with *neither intrinsic dimensions, nor an intrinsic aspect
    ratio*, like a CSS gradient.

CSS determines an object\'s *concrete size* using (1) its *intrinsic
dimensions*; (2) its *specified size*, defined by CSS properties like
[`width`](_Resources/Markup%20And%20Styling/css/width.md), [`height`](_Resources/Markup%20And%20Styling/css/height.md), or
[`background-size`](background-size.md); and (3) its *default size*,
determined by the kind of property the image is used with:

  Kind of Object (CSS Property)                                                             Default object size
  ----------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------
  [`background-image`](background-image.md)                                                    The size of the element\'s background positioning area
  [`list-style-image`](list-style-image.md)                                                    The size of a `1em` character
  [`border-image-source`](border-image-source.md)                                              The size of the element\'s border image area
  [`cursor`](cursor.md)                                                                        The browser-defined size matching the usual cursor size on the client\'s system
  [`mask-image`](mask-image.md)                                                                ?
  [`shape-outside`](shape-outside.md)                                                          ?
  [`mask-border-source`](mask-border-source.md)                                                ?
  [`symbols()`](symbols.md) for \@counter-style                                 At risk feature. If supported, the browser-defined size matching the usual cursor size on the client\'s system
  [`content`](content.md) for a pseudo-element ([`::after`](::after)/[`::before`](::before))   A 300px × 150px rectangle

The concrete object size is calculated using the following algorithm:

- If the specified size defines *both the width and the height*, these
    values are used as the concrete object size.
- If the specified size defines *only the width or only the height*,
    the missing value is determined using the intrinsic ratio, if there
    is any, the intrinsic dimensions if the specified value matches, or
    the default object size for that missing value.
- If the specified size defines *neither the width nor the height*,
    the concrete object size is calculated so that it matches the
    intrinsic aspect ratio of the image but without exceeding the
    default object size in any dimension. If the image has no intrinsic
    aspect ratio, the intrinsic aspect ratio of the object it applies to
    is used; if this object has none, the missing width or height are
    taken from the default object size.

**Note:** Not all browsers support every type of image on every
property. See the [browser compatibility
section](#browser_compatibility) for details.

Accessibility concerns
----------------------

Browsers do not provide any special information on background images to
assistive technology. This is important primarily for screen readers, as
a screen reader will not announce its presence and therefore convey
nothing to its users. If the image contains information critical to
understanding the page\'s overall purpose, it is better to describe it
semantically in the document.

- [MDN Understanding WCAG, Guideline 1.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.1_%E2%80%94_providing_text_alternatives_for_non-text_content)
- [Understanding Success Criterion 1.1.1 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/2016/NOTE-UNDERSTANDING-WCAG20-20161007/text-equiv-all.html)

Formal syntax
-------------

```
<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Valid images

[css]

```css
url(test.jpg)               /* A <url>, as long as test.jpg is an actual image */
linear-gradient(blue, red)  /* A <gradient> */
element(#realid)            /* A part of the webpage, referenced with the element() function,
                               if "realid" is an existing ID on the page */
image(ltr 'arrow.png#xywh=0,0,16,16', red)
                            /* A section 16x16 section of <url>, starting from the top, left of the original
                               image as long as arrow.png is a supported image, otherwise a solid
                               red swatch. If language is rtl, the image will be horizontally flipped. */
cross-fade(20% url(twenty.png), url(eighty.png))
                            /* cross faded images, with twenty being 20% opaque
                               and eighty being 80% opaque. */
image-set('test.jpg' 1x, 'test-2x.jpg' 2x)
                            /* a selection of images with varying resolutions */
```

### Invalid images

[css]

```css
nourl.jpg            /* An image file must be defined using the url() function. */
url(report.pdf)      /* A file pointed to by the url() function must be an image. */
element(#fakeid)     /* An element ID must be an existing ID on the page. */
image(z.jpg#xy=0,0)  /* The spatial fragment must be written in the format of xywh=#,#,#,# */
image-set('cat.jpg' 1x, 'dog.jpg' 1x) /* every image in an image set must have a different resolutions */
```

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [CSS Images Module Level 3\
  [\#
  image-values]](https://drafts.csswg.org/css-images/#image-values)

  ---------------------------------------------------------------------------

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

`image`

1

12

1

10

2

1

4.4

18

4

11

1

1.0

`cross-fade`

17\[\"Supports the original dual-image with percentage implementation
only.\", \"See [bug 614906](https://crbug.com/614906) for supporting the
unprefixed `cross-fade()` function.\"\]

79\[\"Supports the original dual-image with percentage implementation
only.\", \"See [bug 614906](https://crbug.com/614906) for supporting the
unprefixed `cross-fade()` function.\"\]

No

No

15\[\"Supports the original dual-image with percentage implementation
only.\", \"See [bug 614906](https://crbug.com/614906) for supporting the
unprefixed `cross-fade()` function.\"\]

10Supports the original dual-image with percentage implementation only.

5.1Supports the original dual-image with percentage implementation only.

4.4\[\"Supports the original dual-image with percentage implementation
only.\", \"See [bug 614906](https://crbug.com/614906) for supporting the
unprefixed `cross-fade()` function.\"\]

18\[\"Supports the original dual-image with percentage implementation
only.\", \"See [bug 614906](https://crbug.com/614906) for supporting the
unprefixed `cross-fade()` function.\"\]

No

14\[\"Supports the original dual-image with percentage implementation
only.\", \"See [bug 614906](https://crbug.com/614906) for supporting the
unprefixed `cross-fade()` function.\"\]

9.3Support for the original dual-image with percentage implementation
only.

5Supports the original dual-image with percentage implementation only.

1.0\[\"Supports the original dual-image with percentage implementation
only.\", \"See [bug 614906](https://crbug.com/614906) for supporting the
unprefixed `cross-fade()` function.\"\]

`element`

No

No

57

29--57`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`background`](https://developer.mozilla.org/docs/Web/CSS/background),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image)
and
[`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4--29`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image)
and
[`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

No

No

60

29--60`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`background`](https://developer.mozilla.org/docs/Web/CSS/background),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image)
and
[`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4--29`-moz-element()` is limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image)
and
[`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

`gradient`

2610

12

3.6Gradients are limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image),
and
[`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

10

1512.111--15

75.1

≤37≤37

2618

4Gradients are limited to
[`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image),
[`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image),
and
[`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

1412.111--14

75

1.51.0

`image`

No

No

No\[\"See [bug 703217](https://bugzil.la/703217).\", \"The
[`-moz-image-rect()`](https://developer.mozilla.org/docs/Web/CSS/-moz-image-rect)
function supports fragments as of Firefox 4.\"\]

No

No

No

No

No

NoThe
[`-moz-image-rect()`](https://developer.mozilla.org/docs/Web/CSS/-moz-image-rect)
function supports fragments as of Firefox 4.

No

No

No

`image-set`

11321

11379

90

88\[\"In `cursor` and `content` properties, gradients are not supported
as arguments to `image-set()`. See [bug
1696314](https://bugzil.la/1696314).\", \"Before Firefox 89, the
`type()` function is not supported as an argument to `image-set()`.\"\]

No

9915

14

6Support for `url` images only and `x` is the only supported resolution
unit.

1134.4

11325

90

88\[\"In `cursor` and `content` properties, gradients are not supported
as arguments to `image-set()`. See [bug
1696314](https://bugzil.la/1696314).\", \"Before Firefox 89, the
`type()` function is not supported as an argument to `image-set()`.\"\]

14

14

6Support for `url` images only and `x` is the only supported resolution
unit.

1.5

`paint`

65

79

No

No

52

No

65

65

No

47

No

9.2

See also
--------

- [`<gradient>`](gradient.md)
- [`element()`](element().md) [Experimental]
- [`image()`](_Resources/Markup%20And%20Styling/css/image/image.md)
- [`image-set()`](image-set.md)
- [`cross-fade()`](cross-fade.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/image>

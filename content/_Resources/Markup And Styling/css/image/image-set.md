image-set()
===========

The `image-set()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[functional](css_functions.md) notation is a method of letting the
browser pick the most appropriate CSS image from a given set, primarily
for high pixel density screens.

Resolution and bandwidth differ by device and network access. The
`image-set()` function delivers the most appropriate image resolution
for a user\'s device, providing a set of image options --- each with an
associated resolution declaration --- from which the browser picks the
most appropriate for the device and settings. Resolution can be used as
a proxy for filesize --- a user agent on a slow mobile connection with a
high-resolution screen may prefer to receive lower-resolution images
rather than waiting for a higher resolution image to load.

`image-set()` allows the author to provide options rather than
determining what each individual user needs.

Syntax
------

[css]

```css
/* Select image based on resolution */
image-set(
  "image1.jpg" 1x,
  "image2.jpg" 2x
);

image-set(
  url("image1.jpg") 1x,
  url("image2.jpg") 2x
);

/* Select gradient based on resolution */
image-set(
  linear-gradient(blue, white) 1x,
  linear-gradient(blue, green) 2x
);

/* Select image based on supported formats */
image-set(
  url("image1.avif") type("image/avif"),
  url("image2.jpg") type("image/jpeg")
);
```

### Values

[`<image>`](#image)

:   The [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) can be any image type except for an image
    set. The `image-set()` function may not be nested inside another
    `image-set()` function.

[`<string>`](#string)

:   A URL to an image.

[`<resolution>`](#resolution) [Optional]

:   [`<resolution>`](_Resources/Markup%20And%20Styling/css/resolution.md) units include `x` or `dppx`, for
    dots per pixel unit, `dpi`, for dots per inch, and `dpcm` for dots
    per centimeter. Every image within an `image-set()` must have a
    unique resolution.

[`type(<string>)`](#typestring) [Optional]

:   A valid MIME type string, for example \"image/jpeg\".

### Formal syntax

```
<image-set()> = 
  image-set( <image-set-option># )  

<image-set-option> = 
  [ <image> | <string> ] [ <resolution> || type( <string> ) ]  

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Using image-set() to provide alternative background-image options

This example shows how to use
[`image-set()`](https://drafts.csswg.org/css-images-4/#funcdef-image-set)
to provide two alternative [`background-image`](background-image.md)
options, chosen depending on the resolution needed: a normal version and
a high-resolution version.

**Note:** In the above example, the `-webkit` prefixed version is also
used to support Chrome and Safari. In Firefox 90, support was added for
`-webkit-image-set()` as an alias to `image-set()` (in order to provide
compat where developers had not added the standard property).

### Using image-set() to provide alternative image formats

In the next example the `type()` function is used to serve the image in
AVIF and JPEG formats. If the browser supports avif, it will choose that
version. Otherwise it will use the jpeg version.

#### Providing a fallback

There is no inbuilt fallback for `image-set()`; therefore to include a
[`background-image`](background-image.md) for those browsers that do not
support the function, a separate declaration is required before the line
using `image-set()`.

[css]

```css
.box {
  background-image: url("large-balloons.jpg");
  background-image: image-set(
    "large-balloons.avif" type("image/avif"),
    "large-balloons.jpg" type("image/jpeg")
  );
}
```

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

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Images Module Level 4\
  [\#
  image-set-notation]](https://drafts.csswg.org/css-images-4/#image-set-notation)

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

See also
--------

- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [`image()`](_Resources/Markup%20And%20Styling/css/image.md)
- [`element()`](element().md)
- [`url()`](url.md)
- [`<gradient>`](gradient.md)
- [`cross-fade()`](cross-fade.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/image/image-set>

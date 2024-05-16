background-image
================

The `background-image`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
one or more background images on an element.

Try it
------

The background images are drawn on stacking context layers on top of
each other. The first layer specified is drawn as if it is closest to
the user.

The [borders](border.md) of the element are then drawn on top of them, and
the [`background-color`](background-color.md) is drawn beneath them. How
the images are drawn relative to the box and its borders is defined by
the [`background-clip`](background-clip.md) and
[`background-origin`](background-origin.md) CSS properties.

If a specified image cannot be drawn (for example, when the file denoted
by the specified URI cannot be loaded), browsers handle it as they would
a `none` value.

**Note:** Even if the images are opaque and the color won\'t be
displayed in normal circumstances, web developers should always specify
a [`background-color`](background-color.md). If the images cannot be
loaded---for instance, when the network is down---the background color
will be used as a fallback.

Syntax
------

[css]

```css
background-image: linear-gradient(
    to bottom,
    rgba(255, 255, 0, 0.5),
    rgba(0, 0, 255, 0.5)
  ), url("catfront.png");

/* Global values */
background-image: inherit;
background-image: initial;
background-image: revert;
background-image: revert-layer;
background-image: unset;
```

Each background image is specified either as the keyword `none` or as an
[`<image>`](_Resources/Markup%20And%20Styling/css/image.md) value.

To specify multiple background images, supply multiple values, separated
by a comma.

### Values

[`none`](#none)

:   Is a keyword denoting the absence of images.

[`<image>`](#image)

:   Is an [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) denoting the image to display. There can be
    several of them, separated by commas, as [](using_multiple_backgrounds.md)
    are supported.

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

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified, but with [`url()`](url.md) values made absolute
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-image = 
  <bg-image>#  

<bg-image> = 
  <image>  |
  none     

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Layering background images

Note that the star image is partially transparent and is layered over
the cat image.

#### HTML

[html]

```html
<div>
  <p class="catsandstars">This paragraph is full of cats<br />and stars.</p>
  <p>This paragraph is not.</p>
  <p class="catsandstars">Here are more cats for you.<br />Look at them!</p>
  <p>And no more.</p>
</div>
```

#### CSS

[css]

```css
p {
  font-size: 1.5em;
  color: #fe7f88;
  background-image: none;
  background-color: transparent;
}

div {
  background-image: url("mdn_logo_only_color.png");
}

.catsandstars {
  background-image: url("startransparent.gif"), url("catfront.png");
  background-color: transparent;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  [\#
  background-image]](https://drafts.csswg.org/css-backgrounds/#background-image)

  ----------------------------------------------------------------------------------------

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

`background-image`

1

12

1If the `browser.display.use_document_colors` user preference in
`about:config` is set to `false`, background images will not be
displayed.

4

3.5

1

≤37

18

4If the `browser.display.use_document_colors` user preference in
`about:config` is set to `false`, background images will not be
displayed.

14

1

1.0

`element`

No

No

4

No

No

No

No

No

4

No

No

No

`gradients`

1Some versions support only experimental gradients prefixed with
`-webkit`.

12

3.6Some versions support only experimental gradients prefixed with
`-moz`.

10

11Some versions support only experimental gradients prefixed with `-o`.

4Some versions support only experimental gradients prefixed with
`-webkit`.

≤37Some versions support only experimental gradients prefixed with
`-webkit`.

18Some versions support only experimental gradients prefixed with
`-webkit`.

4Some versions support only experimental gradients prefixed with `-moz`.

14Some versions support only experimental gradients prefixed with
`-webkit`.

3.2Some versions support only experimental gradients prefixed with
`-webkit`.

1.0Some versions support only experimental gradients prefixed with
`-webkit`.

`image-rect`

No

No

4

No

No

No

No

No

4

No

No

No

`image-set`

11321

11379

90

88Before Firefox 89, the `type()` function is not supported as an
argument to `image-set()`.

No

9915

14

6Support for `url` images only and `x` is the only supported resolution
unit.

1134.4

11325

90

88Before Firefox 89, the `type()` function is not supported as an
argument to `image-set()`.

14

14

6Support for `url` images only and `x` is the only supported resolution
unit.

1.5

`multiple_backgrounds`

1

12

3.6

9

10.5

1.3

≤37

18

4

14

1

1.0

`svg_images`

8

12

4

9

9.5

5Support of SVG in CSS background is incomplete.

≤37

18

4

14

5Support of SVG in CSS background is incomplete.

1.0

See also
--------

- [](implementing_image_sprites_in_css.md)
- [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)
- Image-related data types: [`<image>`](_Resources/Markup%20And%20Styling/css/image.md),
    [`<gradient>`](gradient.md)
- Image-related functions:
  - [`cross-fade()`](cross-fade.md)
  - [`element()`](element().md)
  - [`image()`](_Resources/Markup%20And%20Styling/css/image/image.md)
  - [`image-set()`](image-set.md)
  - [`linear-gradient()`](linear-gradient.md)
  - [`radial-gradient()`](radial-gradient.md)
  - [`conic-gradient()`](conic-gradient.md)
  - [`repeating-linear-gradient()`](repeating-linear-gradient.md)
  - [`repeating-radial-gradient()`](repeating-radial-gradient.md)
  - [`repeating-conic-gradient()`](repeating-conic-gradient.md)
  - [`paint()`](paint.md)
  - [`url()`](url.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-image>

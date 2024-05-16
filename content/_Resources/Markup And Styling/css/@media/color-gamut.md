color-gamut
===========

The `color-gamut`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](@media.md#media_features) is used to apply CSS styles based on
the approximate range of color
[gamut](https://developer.mozilla.org/en-US/docs/Glossary/Gamut)
supported by the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) and
the output device.

Syntax
------

The `color-gamut` feature is specified as one of the following keyword
values:

[`srgb`](#srgb)

:   The user agent and the output device can support approximately the
    [sRGB](https://en.wikipedia.org/wiki/SRGB) gamut or more. This
    includes the vast majority of color displays.

[`p3`](#p3)

:   The user agent and the output device can support approximately the
    gamut specified by the [Display
    P3](https://www.color.org/chardata/rgb/DisplayP3.xalter) color space
    or more. The P3 gamut is larger than and includes the sRGB gamut.

[`rec2020`](#rec2020)

:   The user agent and the output device can support approximately the
    gamut specified by the [ITU-R Recommendation
    BT.2020](https://en.wikipedia.org/wiki/Rec._2020) color space or
    more. The REC. 2020 gamut is larger than and includes the P3 gamut.

Examples
--------

### HTML

[html]

```html
<p>This is a test.</p>
```

### CSS

```css

[css]

```css

p {
  padding: 10px;
  border: solid;
}

@media (color-gamut: srgb) {
  p {
    background: #f4ae8a;
  }
}

```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  color-gamut]](https://drafts.csswg.org/mediaqueries/#color-gamut)

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

`color-gamut`

58

79

110

No

45

10

58

58

110

43

10

7.0

See also
--------

- [color()](_Resources/Markup%20And%20Styling/css/color_value/color.md) function to specify colors in a
    defined colorspace.
- [\@media](@media.md) at-rule that is used to specify the color-gamut
    expression.
- [Using media queries](using_media_queries.md) to
    understand when and how to use a media query.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media/color-gamut>

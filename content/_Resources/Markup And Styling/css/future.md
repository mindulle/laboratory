:future
=======

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `:future` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector is a time-dimensional
pseudo-class that will match for any element which appears entirely
after an element that matches [`:current`](:current). For example in a
video with captions which are being displayed by
[WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API).

[css]

```css
:future(p, span) {
  display: none;
}
```

Syntax
------

[css]

```css
:future {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:future(p, span) {
  display: none;
}
```

### HTML

[html]

```html
<video controls preload="metadata">
  <source src="video.mp4" type="video/mp4" />
  <source src="video.webm" type="video/webm" />
  <track
    label="English"
    kind="subtitles"
    srclang="en"
    src="subtitles.vtt"
    default />
</video>
```

### WebVTT

```
WEBVTT FILE

1
00:00:03.500 --> 00:00:05.000
This is the first caption

2
00:00:06.000 --> 00:00:09.000
This is the second caption

3
00:00:11.000 --> 00:00:19.000
This is the third caption
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-future-pseudo]](https://drafts.csswg.org/selectors/#the-future-pseudo)

  ------------------------------------------------------------------------------------

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

`:future`

No

No

No

No

No

7

No

No

No

No

7

No

See also
--------

- [Web Video Text Tracks Format
    (WebVTT)](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [`:current`](:current)
- [`:past`](:past)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:future>

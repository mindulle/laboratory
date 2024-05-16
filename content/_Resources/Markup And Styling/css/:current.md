:current
========

The `:current` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector is a time-dimensional
pseudo-class that represents an element or the ancestor of an element
that is currently being displayed. For example, this pseudo-class can be
used to represent a video that is being displayed with captions by
[WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API).

[css]

```css
:current(p, span) {
  background-color: yellow;
}
```

Syntax
------

[css]

```css
:current {
  /* ... */
}

:current(<compound-selector-list>) {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:current(p, span) {
  background-color: yellow;
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

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  the-current-pseudo]](https://drafts.csswg.org/selectors/#the-current-pseudo)

  --------------------------------------------------------------------------------------

Browser compatibility
---------------------

See also
--------

- [Web Video Text Tracks Format
    (WebVTT)](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [`:past`](:past)
- [`:future`](:future)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:current>

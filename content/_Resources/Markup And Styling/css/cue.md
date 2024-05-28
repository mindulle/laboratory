::cue
=====

The `::cue` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) matches
[WebVTT](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
cues within a selected element. This can be used to [style captions and
other
cues](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API#styling_webvtt_cues)
in media with VTT tracks.

Try it
------

The properties are applied to the entire set of cues as if they were a
single unit. The only exception is that `background` and its longhand
properties apply to each cue individually, to avoid creating boxes and
obscuring unexpectedly large areas of the media.

Syntax
------

[css]

```css
::cue | ::cue(<selector>) {
  /* ... */
}
```

Permitted properties
--------------------

Rules whose selectors include this element may only use the following
CSS properties:

- [`background`](background.md)
- [`background-attachment`](background-attachment.md)
- [`background-clip`](background-clip.md)
- [`background-color`](background-color.md)
- [`background-image`](background-image.md)
- [`background-origin`](background-origin.md)
- [`background-position`](background-position.md)
- [`background-repeat`](background-repeat.md)
- [`background-size`](background-size.md)
- [`color`](_Resources/Markup%20And%20Styling/css/color.md)
- [`font`](font.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- [`font-size`](font-size.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [`font-variant`](font-variant.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [`line-height`](line-height.md)
- [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md)
- [`outline`](outline.md)
- [`outline-color`](outline-color.md)
- [`outline-style`](outline-style.md)
- [`outline-width`](outline-width.md)
- [`ruby-position`](ruby-position.md)
- [`text-combine-upright`](text-combine-upright.md)
- [`text-decoration`](text-decoration.md)
- [`text-decoration-color`](text-decoration-color.md)
- [`text-decoration-line`](text-decoration-line.md)
- [`text-decoration-style`](text-decoration-style.md)
- [`text-decoration-thickness`](text-decoration-thickness.md)
- [`text-shadow`](text-shadow.md)
- [`visibility`](visibility.md)
- [`white-space`](white-space.md)

Examples
--------

### Styling WebVTT cues as white-on-black

The following CSS sets the cue style so that the text is white and the
background is a translucent black box.

[css]

```css
::cue {
  color: #fff;
  background-color: rgba(0, 0, 0, 0.6);
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [WebVTT: The Web Video Text Tracks Format\
  [\#
  the-cue-pseudo-element]](https://w3c.github.io/webvtt/#the-cue-pseudo-element)

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

`::cue`

26

79

55From Firefox 69, only allowed properties apply to the `::cue`
pseudo-element with no argument. See [Permitted
properties](https://developer.mozilla.org/docs/Web/CSS/::cue#Permitted_properties)
for a list of the allowed properties.

No

15

7

4.4

26

55

14

7

1.5

`selector_argument`

26

79

No

No

15

7

4.4

26

No

14

7

1.5

See also
--------

- [Web Video Tracks Format
    (WebVTT)](https://developer.mozilla.org/en-US/docs/Web/API/WebVTT_API)
- [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track),
    [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::cue>

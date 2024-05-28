:buffering
==========

The `:buffering` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents an element that is
playable, such as
[`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
when the playable element is buffering a media resource.

An element is considered as buffering when that element cannot continue
playing because it is trying to load media data but does not yet have
enough data to begin or continue playback. For more information, see the
[Media buffering, seeking, and time
ranges](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/buffering_seeking_time_ranges#seekable)
guide.

**Note:** An element is still considered to be [`:playing`](:playing)
when it is \"buffering\". If `:buffering` matches an element, `:playing`
will also match that element.

Syntax
------

[css]

```css
:buffering {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:buffering {
  outline: 5px solid red;
}

video:buffering {
  outline: 5px solid blue;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  selectordef-buffering]](https://drafts.csswg.org/selectors/#selectordef-buffering)

  --------------------------------------------------------------------------------------------

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

`:buffering`

No

No

No

No

No

15.4

No

No

No

No

15.4

No

See also
--------

- [`:muted`](:muted)
- [`:paused`](:paused)
- [`:playing`](:playing)
- [`:seeking`](:seeking)
- [`:stalled`](:stalled)
- [`:volume-locked`](:volume-locked)
- [CSS selectors](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:buffering>

:seeking
========

The `:seeking` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents an element that is
playable, such as
[`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
when the playable element is seeking a playback position in the media
resource. A resource is considered to be seeking if the user has
requested playback of a specific position in the media resource, but the
media element has not yet reached that position.

Seeking is different from [`:buffering`](:buffering) in that the media
element is not currently loading data, but is instead skipping to a new
position in the media resource. For more information, see the [Media
buffering, seeking, and time
ranges](https://developer.mozilla.org/en-US/docs/Web/Guide/Audio_and_video_delivery/buffering_seeking_time_ranges#seekable)
guide.

Syntax
------

[css]

```css
:seeking {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:seeking {
  outline: 5px solid red;
}

video:seeking {
  outline: 5px solid blue;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  selectordef-seeking]](https://drafts.csswg.org/selectors/#selectordef-seeking)

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

`:seeking`

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

- [`:buffering`](:buffering)
- [`:muted`](:muted)
- [`:paused`](:paused)
- [`:playing`](:playing)
- [`:stalled`](:stalled)
- [`:volume-locked`](:volume-locked)
- [CSS selectors](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:seeking>

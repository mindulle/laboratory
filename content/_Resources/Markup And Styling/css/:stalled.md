:stalled
========

The `:stalled` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents an element that is
playable, such as
[`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
when playback is stalled. A resource is considered to be stalled if the
user has requested playback of a specific position in the media
resource, but it has failed to receive any data for some amount of time.
This is different from [`:buffering`](:buffering) in that the media
element is unexpectedly not loading data when stalled (e.g. due to a
network error) for around 3 seconds (the exact time is [user agent
dependent](https://html.spec.whatwg.org/multipage/media.html#stall-timeout)).

**Note:** Like with the [`:buffering`](:buffering) pseudo-class, the
element is still considered to be \"playing\" when it is \"stalled\". If
`:stalled` matches an element, [`:playing`](:playing) will also match
that element.

Syntax
------

[css]

```css
:stalled {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:stalled {
  outline: 5px solid red;
}

audio:stalled {
  background-color: red;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  selectordef-stalled]](https://drafts.csswg.org/selectors/#selectordef-stalled)

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

`:stalled`

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
- [`:seeking`](:seeking)
- [`:volume-locked`](:volume-locked)
- [CSS selectors](css_selectors.md)
- [`stalled`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/stalled_event)
    event

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:stalled>

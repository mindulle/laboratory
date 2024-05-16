:playing
========

The `:playing` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents the playback state of
an element that is playable, such as
[`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
when that element is \"playing\". An element is considered to be playing
if it is currently playing the media resource, or if it has temporarily
stopped for reasons other than user intent (such as
[`:buffering`](:buffering) or [`:stalled`](:stalled)).

Syntax
------

[css]

```css
:playing {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:playing {
  border: 5px solid green;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  selectordef-playing]](https://drafts.csswg.org/selectors/#selectordef-playing)

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

`:playing`

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
- [`:seeking`](:seeking)
- [`:stalled`](:stalled)
- [`:volume-locked`](:volume-locked)
- [CSS selectors](css_selectors.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:playing>

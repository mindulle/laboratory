:volume-locked
==============

The `:volume-locked`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents an element that is
capable of making sound, such as
[`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
but the audio volume of the media element is currently \"locked\" by the
user.

User agents may set media
[`muted`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/muted)
or
[`volume`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/volume)
values according to user preferences (e.g., remembering the last set
value across sessions, on a per-site basis, or otherwise). An element
that is `:volume-locked` cannot be muted, un-muted, or have its volume
changed via JavaScript. The locked status is an operating system or user
agent preference.

Syntax
------

[css]

```css
:volume-locked {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:volume-locked {
  border: 5px solid green;
}

video:volume-locked {
  border: 5px solid aqua;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  selectordef-volume-locked]](https://drafts.csswg.org/selectors/#selectordef-volume-locked)

  ----------------------------------------------------------------------------------------------------

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

`:volume-locked`

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
- [`:stalled`](:stalled)
- [CSS selectors](css_selectors.md)
- [`volume`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/volume)
    property of
    [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    objects

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:volume-locked>

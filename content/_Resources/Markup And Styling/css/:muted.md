:muted
======

The `:muted` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) selector represents an element that is
capable of making sound, such as
[`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
or
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video),
but is muted (forced silent).

Muted is different from [`:volume-locked`](:volume-locked) in that the
page author has control over whether a media element can be muted or
un-muted. User agents may set media `muted` value according to use
preferences (e.g., remembering the last set value across sessions, on a
per-site basis, or otherwise). An element that is `:volume-locked`
cannot be muted, un-muted, or have its volume changed via JavaScript
because of an operating system or user agent preference.

Syntax
------

[css]

```css
:muted {
  /* ... */
}
```

Examples
--------

### CSS

[css]

```css
:muted {
  outline: 5px solid red;
}

video:muted {
  outline: 5px solid blue;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  selectordef-muted]](https://drafts.csswg.org/selectors/#selectordef-muted)

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

`:muted`

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
- [`:paused`](:paused)
- [`:playing`](:playing)
- [`:seeking`](:seeking)
- [`:stalled`](:stalled)
- [`:volume-locked`](:volume-locked)
- [CSS selectors](css_selectors.md)
- [`muted`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/muted)
    property of
    [`HTMLMediaElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement)
    objects

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:muted>

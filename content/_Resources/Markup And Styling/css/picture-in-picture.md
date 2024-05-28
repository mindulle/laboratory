:picture-in-picture
===================

The `:picture-in-picture`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches the element which is currently in
picture-in-picture mode.

Syntax
------

[css]

```css
:picture-in-picture {
  /* ... */
}
```

Usage notes
-----------

The `:picture-in-picture` pseudo-class lets you configure your
stylesheets to automatically adjust the size, style, or layout of
content when a video switches back and forth between picture-in-picture
and traditional presentation modes.

Examples
--------

In this example, a video has a box shadow when it is displayed in the
floating window.

### HTML

The page\'s HTML looks like this:

[html]

```html
<h1>MDN Web Docs Demo: :picture-in-picture pseudo-class</h1>

<p>
  This demo uses the <code>:picture-in-picture</code> pseudo-class to
  automatically change the style of a video entirely using CSS.
</p>

<video id="pip-video"></video>
```

The
[`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
with the ID `"pip-video"` will change between having a red box shadow or
not, depending on whether or not it is displayed in the
picture-in-picture floating window.

### CSS

The magic happens in the CSS.

[css]

```css
:picture-in-picture {
  box-shadow: 0 0 0 5px red;
}
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  [\# pip-state]](https://drafts.csswg.org/selectors/#pip-state)

  -----------------------------------------------------------------------

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

`:picture-in-picture`

110

110

No

No

96

No

110

110

No

74

No

21.0

See also
--------

- [Picture-in-picture
    API](https://developer.mozilla.org/en-US/docs/Web/API/Picture-in-Picture_API)
- [`HTMLVideoElement.requestPictureInPicture()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/requestPictureInPicture)
- [`HTMLVideoElement.disablePictureInPicture`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/disablePictureInPicture)
- [`Document.pictureInPictureEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureEnabled)
- [`Document.exitPictureInPicture()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPictureInPicture)
- [`Document.pictureInPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureElement)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture>

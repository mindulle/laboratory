HTML attribute: capture
=======================

The `capture` attribute specifies that, optionally, a new file should be
captured, and which device should be used to capture that new media of a
type defined by the [`accept`](accept) attribute.

Values include `user` and `environment`. The capture attribute is
supported on the [file](../element/input/file) input type.

The `capture` attribute takes as its value a string that specifies which
camera to use for capture of image or video data, if the
[accept](accept) attribute indicates that the input should be of one of
those types.

  Value           Description
  --------------- ------------------------------------------------------------
  `user`          The user-facing camera and/or microphone should be used.
  `environment`   The outward-facing camera and/or microphone should be used

**Note:** Capture was previously a Boolean attribute which, if present,
requested that the device\'s media capture device(s) such as camera or
microphone be used instead of requesting a file input.

Try it
------

Examples
--------

When set on a file input type, operating systems with microphones and
cameras will display a user interface allowing the selection from an
existing file or the creating of a new one.

[html]

```html
<p>
  <label for="soundFile">What does your voice sound like?:</label>
  <input type="file" id="soundFile" capture="user" accept="audio/*" />
</p>
<p>
  <label for="videoFile">Upload a video:</label>
  <input type="file" id="videoFile" capture="environment" accept="video/*" />
</p>
<p>
  <label for="imageFile">Upload a photo of yourself:</label>
  <input type="file" id="imageFile" capture="user" accept="image/*" />
</p>
```

Note these work better on mobile devices; if your device is a desktop
computer, you\'ll likely get a typical file picker.

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [HTML Media Capture\
  [\#
  dfn-capture]](https://w3c.github.io/html-media-capture/#dfn-capture)

  ------------------------------------------------------------------------------

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

`capture`

No

No

No

No

No

No

4.4

25

79

14

10

1.5

See also
--------

- [Using files from web
    applications](https://developer.mozilla.org/en-US/docs/Web/API/File_API/Using_files_from_web_applications)
- [File API](https://developer.mozilla.org/en-US/docs/Web/API/File)
- [`HTMLInputElement.files`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/files)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/capture>>

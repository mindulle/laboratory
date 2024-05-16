\<image\>: The Image element
============================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

**Non-standard:** This feature is non-standard and is not on a standards
track. Do not use it on production sites facing the Web: it will not
work for every user. There may also be large incompatibilities between
implementations and the behavior may change in the future.

The `<image>` [HTML](../index) element is an ancient and poorly
supported precursor to the [`<img>`](img) element. **It should not be
used**.

Some browsers will attempt to automatically convert this into an
[`<img>`](img) element, and may succeed if the [`src`](img#src)
attribute is specified as well.

Specifications
--------------

This does not appear to have been part of any formal specification. It
was mentioned in [HTML+ Discussion Document - Dave Raggett, November 8,
1993](https://www.w3.org/MarkUp/HTMLPlus/htmlplus_21.html) (Section 5.9

- Images), but was not part of the first revision of [HyperText Markup
Language Specification -
2.0](https://datatracker.ietf.org/doc/html/draft-ietf-html-spec-00) in

1994.

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

`image`

1

79

1Before Firefox 22, creating an \<image\> element incorrectly resulted
in an `HTMLSpanElement` object, instead of the expected `HTMLElement`.

No

15

1

4.4

18

4Before Firefox 22, creating an \<image\> element incorrectly resulted
in an `HTMLSpanElement` object, instead of the expected `HTMLElement`.

14

1

1.0

See also
--------

- [`<img>`](img): The correct way to display an image in a document
- [`<picture>`](picture): A more powerful correct way to display an
    image in a document

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/image>>

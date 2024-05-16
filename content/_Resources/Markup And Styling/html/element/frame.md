\<frame\>
=========

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<frame>` [HTML](../index) element defines a particular area in
which another HTML document can be displayed. A frame should be used
within a [`<frameset>`](frameset).

Using the `<frame>` element is not encouraged because of certain
disadvantages such as performance problems and lack of accessibility for
users with screen readers. Instead of the `<frame>` element,
[`<iframe>`](iframe) may be preferred.

Attributes
----------

Like all other HTML elements, this element supports the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`src`](#src) [Deprecated]

:   This attribute specifies the document that will be displayed by the
    frame.

[`name`](#name) [Deprecated]

:   This attribute is used for labeling frames. Without labeling, every
    link will open in the frame that it\'s in -- the closest parent
    frame. See the [`target`](a#target) attribute for more information.

[`noresize`](#noresize) [Deprecated]

:   This attribute prevents resizing of frames by users.

[`scrolling`](#scrolling) [Deprecated]

:   This attribute defines the existence of a scrollbar. If this
    attribute is not used, the browser adds a scrollbar when necessary.
    There are two choices: \"yes\" for forcing a scrollbar even when it
    is not necessary and \"no\" for forcing no scrollbar even when it
    *is* necessary.

[`marginheight`](#marginheight) [Deprecated]

:   This attribute defines the height of the margin between frames.

[`marginwidth`](#marginwidth) [Deprecated]

:   This attribute defines the width of the margin between frames.

[`frameborder`](#frameborder) [Deprecated]

:   This attribute allows you to specify a frame\'s border.

Example
-------

### A frameset document

A frameset document has a [`<frameset>`](frameset) element instead of a
[`<body>`](body) element. The `<frame>` elements are placed within the
`<frameset>`.

[html]

```html
<!doctype html>
<html lang="en-US">
  <head>
    <!-- Document metadata goes here -->
  </head>
  <frameset cols="400, 500">
    <frame src="https://developer.mozilla.org/en/HTML/Element/iframe" />
    <frame src="https://developer.mozilla.org/en/HTML/Element/frame" />
  </frameset>
</html>
```

If you want to embed another HTML page into the [`<body>`](body) of a
document, use an [`<iframe>`](iframe) element.

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [HTML Standard\
  [\#
  frame]](https://html.spec.whatwg.org/multipage/obsolete.html#frame)

  -----------------------------------------------------------------------------

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

`frame`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`frameborder`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`marginheight`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`marginwidth`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`name`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`noresize`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`scrolling`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

`src`

1

12

1

Yes

15

3

4.4

18

4

14

2

1.0

See also
--------

- [`<frameset>`](frameset)
- [`<iframe>`](iframe)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame>>

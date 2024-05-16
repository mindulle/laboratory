\<source\>: The Media or Image Source element
=============================================

The `<source>` [HTML](../index) element specifies multiple media
resources for the [`<picture>`](picture), the [`<audio>`](audio)
element, or the [`<video>`](video) element. It is a [void
element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element),
meaning that it has no content and does not have a closing tag. It is
commonly used to offer the same media content in multiple file formats
in order to provide compatibility with a broad range of browsers given
their differing support for [image file
formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
and [media file
formats](https://developer.mozilla.org/en-US/docs/Web/Media/Formats).

Try it
------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  It must have a start tag, but must not have an end tag.
  Permitted parents                             A media element---[`<audio>`](audio) or [`<video>`](video)---and it must be placed before any [flow content](../content_categories#flow_content) or [`<track>`](track) element. A [`<picture>`](picture) element, and it must be placed before the [`<img>`](img) element.
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLSourceElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSourceElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`type`](#type)

:   The [MIME media type of the
    image](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
    or [other media
    type](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Containers),
    optionally with a [`codecs`
    parameter](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/codecs_parameter).

[`src`](#src)

:   Required if the `source` element\'s parent is an [`<audio>`](audio)
    and [`<video>`](video) element, but not allowed if the `source`
    element\'s parent is a [`<picture>`](picture) element.

    Address of the media resource.

[`srcset`](#srcset)

:   Required if the `source` element\'s parent is a
    [`<picture>`](picture) element, but not allowed if the `source`
    element\'s parent is an [`<audio>`](audio) or [`<video>`](video)
    element.

    A list of one or more strings, separated by commas, indicating a set
    of possible images represented by the source for the browser to use.
    Each string is composed of:

    1.  One URL specifying an image.
    2.  A width descriptor, which consists of a string containing a
        positive integer directly followed by `"w"`, such as `300w`. The
        default value, if missing, is the infinity.
    3.  A pixel density descriptor, that is a positive floating number
        directly followed by `"x"`. The default value, if missing, is
        `1x`.

    Each string in the list must have at least a width descriptor or a
    pixel density descriptor to be valid. The two types of descriptors
    should not be mixed together and only one should be used
    consistently throughout the list. Among the list, the value of each
    descriptor must be unique. The browser chooses the most adequate
    image to display at a given point of time. If the `sizes` attribute
    is present, then a width descriptor must be specified for each
    string. If the browser does not support `srcset`, then `src` will be
    used for the default source.

[`sizes`](#sizes)

:   Allowed if the `source` element\'s parent is a
    [`<picture>`](picture) element, but not allowed if the `source`
    element\'s parent is an [`<audio>`](audio) or [`<video>`](video)
    element.

    A list of source sizes that describes the final rendered width of
    the image represented by the source. Each source size consists of a
    comma-separated list of media condition-length pairs. Before laying
    the page out, the browser uses this information to determine which
    image is defined in [`srcset`](#srcset) to use. Please note that
    `sizes` will have its effect only if width dimension descriptors are
    provided with `srcset` instead of pixel ratio values (200w instead
    of 2x for example).

[`media`](#media)

:   [Media
    query](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries)
    of the resource\'s intended media.

[`height`](#height)

:   Allowed if the `source` element\'s parent is a
    [`<picture>`](picture) element, but not allowed if the `source`
    element\'s parent is an [`<audio>`](audio) or [`<video>`](video)
    element.

    The intrinsic height of the image, in pixels. Must be an integer
    without a unit.

[`width`](#width)

:   Allowed if the `source` element\'s parent is a
    [`<picture>`](picture) element, but not allowed if the `source`
    element\'s parent is an [`<audio>`](audio) or [`<video>`](video)
    element.

    The intrinsic width of the image in pixels. Must be an integer
    without a unit.

If the `type` attribute isn\'t specified, the media\'s type is retrieved
from the server and checked to see if the user agent can handle it; if
it can\'t be rendered, the next `<source>` is checked. If the `type`
attribute is specified, it\'s compared against the types the user agent
can present, and if it\'s not recognized, the server doesn\'t even get
queried; instead, the next `<source>` element is checked at once.

When used in the context of a `<picture>` element, the browser will fall
back to using the image specified by the `<picture>` element\'s
[`<img>`](img) child if it is unable to find a suitable image to use
after examining every provided `<source>`.

Usage notes
-----------

The `<source>` element is a **[void
element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element)**,
which means that it not only has no content but also has no closing tag.
That is, you *never* use \"`</source>`\" in your HTML.

For information about image formats supported by web browsers and
guidance on selecting appropriate formats to use, see our [Image file
type and format
guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
on the web. For details on the video and audio media types you can use,
see the [Guide to media types formats used on the
web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats).

Examples
--------

### Video with type attribute example

This example demonstrates how to offer a video in WebM format for users
whose browsers support WebM format, Ogg format for users whose browsers
support Ogg format, and a QuickTime format video for users whose
browsers support that. If the `audio` or `video` element is not
supported by the browser, a notice is displayed instead. If the browser
supports the element but does not support any of the specified formats,
an `error` event is raised and the default media controls (if enabled)
will indicate an error. Be sure to reference our [guide to media types
and formats on the
web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats) for
details on what media file formats you can use and how well they\'re
supported by browsers.

[html]

```html
<video controls>
  <source src="foo.webm" type="video/webm" />
  <source src="foo.ogg" type="video/ogg" />
  <source src="foo.mov" type="video/quicktime" />
  I'm sorry; your browser doesn't support HTML video.
</video>
```

### Video with media attribute example

This example demonstrates how to offer an alternate source file for
viewports at or above a certain width. When a user\'s browsing
environment meets the specified `media` condition, the associated
`<source>` element is chosen, and the contents of its `src` attribute
are requested and rendered. If the `media` condition does not match, the
user agent will move on to the next `<source>` in the source order. The
second source option in the below code has no `media` condition, so will
be selected for all other browsing contexts.

[html]

```html
<video controls>
  <source src="foo-large.webm" media="(min-width: 800px)" />
  <source src="foo.webm" />
  I'm sorry; your browser doesn't support HTML video.
</video>
```

For more examples, the learning area article [Video and audio
content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
is a great resource.

### Picture example

In this example, two `<source>` elements are included within the
[`<picture>`](picture), providing versions of an image to use when the
available space exceeds certain widths. If the available width is less
than the smallest of these widths, the user agent will fall back to the
image given by the [`<img>`](img) element.

[html]

```html
<picture>
  <source srcset="mdn-logo-wide.png" media="(min-width: 800px)" />
  <source srcset="mdn-logo-medium.png" media="(min-width: 600px)" />
  <img src="mdn-logo-narrow.png" alt="MDN Web Docs" />
</picture>
```

With the `<picture>` element, you must always include an `<img>` with a
fallback image, with an `alt` attribute to ensure accessibility (unless
the image is an irrelevant background decorative image).

### Picture with height & width attributes example

In this example, three `<source>` elements with `height` and `width`
attributes are included in a [`<picture>`](picture) element. A [media
query](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries)
allows the browser to select an image to display with the `height` and
`width` attributes based on the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
size.

[html]

```html
<picture>
  <source
    srcset="landscape.png"
    media="(min-width: 1000px)"
    width="1000"
    height="400" />
  <source
    srcset="square.png"
    media="(min-width: 800px)"
    width="800"
    height="800" />
  <source
    srcset="portrait.png"
    media="(min-width: 600px)"
    width="600"
    height="800" />
  <img
    src="fallback.png"
    alt="Image used when the browser does not support the sources"
    width="500"
    height="400" />
</picture>
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-source-element]](https://html.spec.whatwg.org/multipage/embedded-content.html#the-source-element)

  ---------------------------------------------------------------------------------------------------------------

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

`source`

3

12

3.5Until Firefox 15, Firefox picked the first source element that has a
type matching the MIME-type of a supported media format; see [bug
449363](https://bugzil.la/449363) for details.

9

15

3.1

4.4

18

4Until Firefox 15, Firefox picked the first source element that has a
type matching the MIME-type of a supported media format; see [bug
449363](https://bugzil.la/449363) for details.

14

2

1.0

`height`

90

90

108

9

76

15

90

90

108

64

15

15.0

`media`

3

12

15

9

15

3.1

4.4

18

15

14

2

1.0

`sizes`

38

34--38Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

≤18

38

No

25

21--25Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

9.1

38

37--38Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

38

34--38Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

38

25

21--25Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

9.3

3.0

2.0--3.0Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

`src`

3

12

3.5

9

15

3.1

4.4

18

4

14

2

1.0

`srcset`

38

34--38Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

≤18

38

No

25

21--25Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

9.1

38

37--38Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

38

34--38Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

38

25

21--25Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

9.3

3.0

2.0--3.0Supports a subset of the syntax for resolution switching (using
the `x` descriptor), but not the full syntax that can be used with
`sizes` (using the `w` descriptor).

`type`

3

12

3.5

9

15

3.1

4.4

18

4

14

2

1.0

`width`

90

90

108

9

76

15

90

90

108

64

15

15.0

See also
--------

- [Guide to media types and formats on the
    web](https://developer.mozilla.org/en-US/docs/Web/Media/Formats)
- [Image file type and format
    guide](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/Image_types)
- [`<picture>`](picture) element
- [`<audio>`](audio) element
- [`<video>`](video) element
- [Web
    Performance](https://developer.mozilla.org/en-US/docs/Learn/Performance)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source>>

cursor
======

The `cursor` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the mouse cursor, if any, to show when the mouse pointer
is over an element.

The cursor setting should inform users of the mouse operations that can
be performed at the current location, including: text selection,
activating help or context menus, copying content, resizing tables, and
so on. You can specify either the *type* of cursor using a keyword, or
load a specific icon to use (with optional fallback images and mandatory
keyword as a final fallback).

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
cursor: auto;
cursor: pointer;
/* … */
cursor: zoom-out;

/* URL with mandatory keyword fallback */
cursor: url(hand.cur), pointer;

/* URL and coordinates, with mandatory keyword fallback */
cursor:
  url(cursor_1.png) 4 12,
  auto;
cursor:
  url(cursor_2.png) 2 2,
  pointer;

/* URLs and fallback URLs (some with coordinates), with mandatory keyword fallback */
cursor:
  url(cursor_1.svg) 4 5,
  url(cursor_2.svg),
  /* …, */ url(cursor_n.cur) 5 5,
  progress;

/* Global values */
cursor: inherit;
cursor: initial;
cursor: revert;
cursor: revert-layer;
cursor: unset;
```

The `cursor` property is specified as zero or more `<url>` values,
separated by commas, followed by a single mandatory keyword value. Each
`<url>` should point to an image file. The browser will try to load the
first image specified, falling back to the next if it can\'t, and
falling back to the keyword value if no images could be loaded (or if
none were specified).

Each `<url>` may be optionally followed by a pair of space-separated
numbers, which set the `<x>` and `<y>` coordinates of the cursor\'s
hotspot relative to the top-left corner of the image.

### Values

[`<url>`](#url) [Optional]

:   A `url()` or a comma separated list `url(), url(), …`, pointing to
    an image file. More than one [`url()`](url.md) may be provided as
    fallbacks, in case some cursor image types are not supported. A
    non-URL fallback (one or more of the keyword values) *must* be at
    the end of the fallback list.

[`<x>`](#x), `<y>` [Optional]

:   Optional x- and y-coordinates indicating the cursor hotspot; the
    precise position within the cursor that is being pointed to.

    The numbers are in units of image pixels. They are relative to the
    top left corner of the image, which corresponds to \"`0 0`\", and
    are clamped within the boundaries of the cursor image. If these
    values are not specified, they may be read from the file itself, and
    will otherwise default to the top-left corner of the image.

[`keyword`](#keyword)

:   A keyword value *must* be specified, indicating either the type of
    cursor to use, or the fallback cursor to use if all specified icons
    fail to load.

    The available keywords are listed in the table below. Other than
    `none`, which means no cursor, there is an image showing how the
    cursors used to be rendered. You can hover your mouse over the table
    rows to see the effect of the different cursor keyword values on
    your browser today.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified, but with [`url()`](url.md) values made absolute
  Animation type                     discrete
  ---------------------------------- ------------------------------------------------------------

Formal syntax
-------------

```text
cursor = 
  [ [ <url> | <url-set> ] [ <x> <y> ]? ]#? [ auto | default | none | context-menu | help | pointer | progress | wait | cell | crosshair | text | vertical-text | alias | copy | move | no-drop | not-allowed | grab | grabbing | e-resize | n-resize | ne-resize | nw-resize | s-resize | se-resize | sw-resize | w-resize | ew-resize | ns-resize | nesw-resize | nwse-resize | col-resize | row-resize | all-scroll | zoom-in | zoom-out ]  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Usage notes
-----------

### Icon size limits

While the specification does not limit the `cursor` image size, [user
agents](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
commonly restrict them to avoid potential misuse. For example, on
Firefox and Chromium cursor images are restricted to 128x128 pixels by
default, but it is recommended to limit the cursor image size to 32x32
pixels. Cursor changes using images that are larger than the user-agent
maximum supported size will generally just be ignored.

### Supported image file formats

User agents are required by the specification to support PNG files, SVG
v1.1 files in secure static mode that contain a natural size, and any
other non-animated image file formats that they support for images in
other properties. Desktop browsers also broadly support the `.cur` file
format.

The specification further indicates that user agents *should* also
support SVG v1.1 files in secure animated mode that contain a natural
size, along with any other animated images file formats they support for
images in other properties. User agents *may* support both static and
animated SVG images that do not contain a natural size.

### iPadOS

iPadOS supports pointer devices like trackpads and mouses. By default,
the iPad cursor is displayed as a circle, and the only supported value
that will change an appearance of the pointer is `text`.

### Other notes

Cursor changes that intersect toolbar areas are commonly blocked to
avoid spoofing.

Examples
--------

### Setting cursor types

[css]

```css
.foo {
  cursor: crosshair;
}

.bar {
  cursor: zoom-in;
}

/* A fallback keyword value is required when using a URL */
.baz {
  cursor: url("hyper.cur"), auto;
}
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Basic User Interface Module Level 4\
  [\# cursor]](https://drafts.csswg.org/css-ui/#cursor)

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

`cursor`

1

12

1Starting in Firefox 67, the maximum size allowed for custom cursors is
32x32 pixels due to cursors being misused by certain malicious sites.

4In Internet Explorer 11, when `cursor` is applied to an element and
this element is underneath an open
[`<select>`](https://developer.mozilla.org/docs/Web/HTML/Element/select)
menu and the user hovers over a
[`<select>`](https://developer.mozilla.org/docs/Web/HTML/Element/select)
menu item that\'s on top of said element, the cursor for said element
will be displayed rather than the
[`<select>`](https://developer.mozilla.org/docs/Web/HTML/Element/select)\'s
normal cursor. See [bug
817822](https://developer.microsoft.com/microsoft-edge/platform/issues/817822/).

7

1.2

4.4

18

95

14

1

1.0

`alias`

1

12

1.5

10

10.6

3

4.4

18

95

14

1

1.0

`all-scroll`

1

12

1.5

6

10.6

3

4.4

18

95

14

1

1.0

`auto`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`bidirectional_resize`

1

12

1.5

10

10.6

3

4.4

18

95

14

1

1.0

`cell`

1

12

1.5

10

10.6

3

4.4

18

95

14

1

1.0

`col-resize`

1

12

1.5

6

10.6

3

4.4

18

95

14

1

1.0

`context-menu`

1This cursor is only supported on macOS and Linux.

12

1.5This cursor is only supported on macOS and Linux.

10

10.6

3

4.4This cursor is only supported on macOS and Linux.

18This cursor is only supported on macOS and Linux.

95

14This cursor is only supported on macOS and Linux.

1

1.0This cursor is only supported on macOS and Linux.

`copy`

1

12

1.5

10

10.6

3

4.4

18

95

14

1

1.0

`crosshair`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`default`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`grab`

68Chrome also continues to support the prefixed versions.

1Chrome 22 added Windows support.

14

271.5

No

55Opera also continues to support the prefixed versions.

15Opera 22 added Windows support.

114

68Chrome also continues to support the prefixed versions.

4.4Chrome 22 added Windows support.

68Chrome also continues to support the prefixed versions.

18Chrome 22 added Windows support.

95

48Opera also continues to support the prefixed versions.

14Opera 22 added Windows support.

1

10.01.0

`help`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`inherit`

1

12

1

8

9

1.2

4.4

18

95

14

1

1.0

`move`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`no-drop`

1

12

1.5

6

10.6

3

4.4

18

95

14

1

1.0

`none`

5

12

3

9

15

5

4.4

18

95

14

4.2

1.0

`not-allowed`

1

12

1.5

6

10.6

3

4.4

18

95

14

1

1.0

`pointer`

1

12

1

6

7

1.2

4.4

18

95

14

1

1.0

`progress`

1

12

1

6

7

1.2

4.4

18

95

14

1

1.0

`row-resize`

1

12

1.5

6

10.6

3

4.4

18

95

14

1

1.0

`text`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`unidirectional_resize`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`url`

1

12

1.5Firefox 4 added macOS support.

6

15

3

4.4

18

95

14

1

1.0

`url_positioning_syntax`

1

79

1.5Firefox 4 added macOS support.

No

15

3

4.4

18

95

14

1

1.0

`vertical-text`

1

12

1.5

No

10.6

3

4.4

18

95

14

1

1.0

`wait`

1

12

1

4

7

1.2

4.4

18

95

14

1

1.0

`zoom`

371

12

241

No

2415--23

93

374.4

3718

95

2414--24

1

3.01.0

See also
--------

- [`pointer-events`](pointer-events.md)
- [`url()`](url.md) function

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/cursor>

\<head\>: The Document Metadata (Header) element
================================================

The `<head>` [HTML](../index) element contains machine-readable
information
([metadata](https://developer.mozilla.org/en-US/docs/Glossary/Metadata))
about the document, like its [title](title), [scripts](script), and
[style sheets](style).

**Note:** `<head>` primarily holds information for machine processing,
not human-readability. For human-visible information, like top-level
headings and listed authors, see the [`<header>`](header) element.

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`profile`](#profile) [Deprecated]

:   The [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI)s of
    one or more metadata profiles, separated by [white
    space](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace).

Examples
--------

[html]

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Document title</title>
  </head>
</html>
```

Technical summary
-----------------

+-----------------------------------+-----------------------------------+
| [Content                          | None.                             |
| c                                 |                                   |
| ategories](../content_categories) |                                   |
+-----------------------------------+-----------------------------------+
| Permitted content                 | If the document is an             |
|                                   | [`<iframe>`](iframe)              |
|                                   | [`srcdoc`](iframe#srcdoc)         |
|                                   | document, or if title information |
|                                   | is available from a higher level  |
|                                   | protocol (like the subject line   |
|                                   | in HTML email), zero or more      |
|                                   | elements of metadata content.     |
|                                   |                                   |
|                                   | Otherwise, one or more elements   |
|                                   | of metadata content where exactly |
|                                   | one is a [`<title>`](title)       |
|                                   | element.                          |
+-----------------------------------+-----------------------------------+
| Tag omission                      | The start tag may be omitted if   |
|                                   | the first thing inside the        |
|                                   | `<head>` element is an element.\  |
|                                   | The end tag may be omitted if the |
|                                   | first thing following the         |
|                                   | `<head>` element is not a space   |
|                                   | character or a comment.           |
+-----------------------------------+-----------------------------------+
| Permitted parents                 | An [`<html>`](html) element, as   |
|                                   | its first child.                  |
+-----------------------------------+-----------------------------------+
| Implicit ARIA role                | [No corresponding                 |
|                                   | role](https://www.w3.org/TR/html>>  |
|                                   | -aria/#dfn-no-corresponding-role) |
+-----------------------------------+-----------------------------------+
| Permitted ARIA roles              | No `role` permitted               |
+-----------------------------------+-----------------------------------+
| DOM interface                     | [`HTMLHeadElement`]               |
|                                   | (https://developer.mozilla.org/en>> |
|                                   | -US/docs/Web/API/HTMLHeadElement) |
+-----------------------------------+-----------------------------------+

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-head-element]](https://html.spec.whatwg.org/multipage/semantics.html#the-head-element)

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

`head`

1

12

1

Yes

15

1

4.4

18

4

14

1

1.0

`profile`

1

12

1

Yes

15

1--16.4

4.4

18

4

14

1--16.4

1.0

See also
--------

- Elements that can be used inside the `<head>`:
  - [`<title>`](title)
  - [`<base>`](base)
  - [`<link>`](link)
  - [`<style>`](style)
  - [`<meta>`](meta)
  - [`<script>`](script)
  - [`<noscript>`](noscript)
  - [`<template>`](template)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head>>

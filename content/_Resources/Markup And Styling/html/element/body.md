\<body\>: The Document Body element
===================================

The `<body>` [HTML](../index) element represents the content of an HTML
document. There can be only one `<body>` element in a document.

+-----------------------------------+-----------------------------------+
| [Content                          | None.                             |
| c                                 |                                   |
| ategories](../content_categories) |                                   |
+-----------------------------------+-----------------------------------+
| Permitted content                 | [Flow                             |
|                                   | content](../                      |
|                                   | content_categories#flow_content). |
+-----------------------------------+-----------------------------------+
| Tag omission                      | The start tag may be omitted if   |
|                                   | the first thing inside it is not  |
|                                   | a space character, comment,       |
|                                   | [`<script>`](script) element or   |
|                                   | [`<style>`](style) element. The   |
|                                   | end tag may be omitted if the     |
|                                   | `<body>` element has contents or  |
|                                   | has a start tag, and is not       |
|                                   | immediately followed by a         |
|                                   | comment.                          |
+-----------------------------------+-----------------------------------+
| Permitted parents                 | It must be the second element of  |
|                                   | an [`<html>`](html) element.      |
+-----------------------------------+-----------------------------------+
| Implicit ARIA role                | `generic`                         |
+-----------------------------------+-----------------------------------+
| Permitted ARIA roles              | No `role` permitted               |
+-----------------------------------+-----------------------------------+
| DOM interface                     | [`HTMLBodyElement`]               |
|                                   | (https://developer.mozilla.org/en>> |
|                                   | -US/docs/Web/API/HTMLBodyElement) |
|                                   |                                   |
|                                   | -   The `<body>` element exposes  |
|                                   |     the                           |
|                                   |     [`HTMLBodyElement`]           |
|                                   | (https://developer.mozilla.org/en>> |
|                                   | -US/docs/Web/API/HTMLBodyElement) |
|                                   |     interface.                    |
|                                   | -   You can access the `<body>`   |
|                                   |     element through the           |
|                                   |     [`document.body               |
|                                   |`](https://developer.mozilla.org/>> |
|                                   | en-US/docs/Web/API/Document/body) |
|                                   |     property.                     |
+-----------------------------------+-----------------------------------+

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`alink`](#alink) [Deprecated]

:   Color of text for hyperlinks when selected. **Do not use this
    attribute! Use the CSS
    [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
    property in conjunction with the
    [`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active)
    pseudo-class instead.**

[`background`](#background) [Deprecated]

:   URI of an image to use as a background. **Do not use this attribute!
    Use the CSS
    [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background)
    property on the element instead.**

[`bgcolor`](#bgcolor) [Deprecated]

:   Background color for the document. **Do not use this attribute! Use
    the CSS
    [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)
    property on the element instead.**

[`bottommargin`](#bottommargin) [Deprecated]

:   The margin of the bottom of the body. **Do not use this attribute!
    Use the CSS
    [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom)
    property on the element instead.**

[`leftmargin`](#leftmargin) [Deprecated]

:   The margin of the left of the body. **Do not use this attribute! Use
    the CSS
    [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)
    property on the element instead.**

[`link`](#link) [Deprecated]

:   Color of text for unvisited hypertext links. **Do not use this
    attribute! Use the CSS
    [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
    property in conjunction with the
    [`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link)
    pseudo-class instead.**

[`onafterprint`](#onafterprint)

:   Function to call after the user has printed the document.

[`onbeforeprint`](#onbeforeprint)

:   Function to call when the user requests printing of the document.

[`onbeforeunload`](#onbeforeunload)

:   Function to call when the document is about to be unloaded.

[`onblur`](#onblur)

:   Function to call when the document loses focus.

[`onerror`](#onerror)

:   Function to call when the document fails to load properly.

[`onfocus`](#onfocus)

:   Function to call when the document receives focus.

[`onhashchange`](#onhashchange)

:   Function to call when the fragment identifier part (starting with
    the hash (`'#'`) character) of the document\'s current address has
    changed.

[`onlanguagechange`](#onlanguagechange)

:   Function to call when the preferred languages changed.

[`onload`](#onload)

:   Function to call when the document has finished loading.

[`onmessage`](#onmessage)

:   Function to call when the document has received a message.

[`onoffline`](#onoffline)

:   Function to call when network communication has failed.

[`ononline`](#ononline)

:   Function to call when network communication has been restored.

[`onpopstate`](#onpopstate)

:   Function to call when the user has navigated session history.

[`onredo`](#onredo)

:   Function to call when the user has moved forward in undo transaction
    history.

[`onresize`](#onresize)

:   Function to call when the document has been resized.

[`onstorage`](#onstorage)

:   Function to call when the storage area has changed.

[`onundo`](#onundo)

:   Function to call when the user has moved backward in undo
    transaction history.

[`onunload`](#onunload)

:   Function to call when the document is going away.

[`rightmargin`](#rightmargin) [Deprecated]

:   The margin of the right of the body. **Do not use this attribute!
    Use the CSS
    [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right)
    property on the element instead.**

[`text`](#text) [Deprecated]

:   Foreground color of text. **Do not use this attribute! Use CSS
    [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
    property on the element instead.**

[`topmargin`](#topmargin) [Deprecated]

:   The margin of the top of the body. **Do not use this attribute! Use
    the CSS
    [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top)
    property on the element instead.**

[`vlink`](#vlink) [Deprecated]

:   Color of text for visited hypertext links. **Do not use this
    attribute! Use the CSS
    [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color)
    property in conjunction with the
    [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited)
    pseudo-class instead.**

Examples
--------

[html]

```html
<html lang="en">
  <head>
    <title>Document title</title>
  </head>
  <body>
    <p>
      The <code>&lt;body&gt;</code> HTML element represents the content of an
      HTML document. There can be only one <code>&lt;body&gt;</code> element in
      a document.
    </p>
  </body>
</html>
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-body-element]](https://html.spec.whatwg.org/multipage/sections.html#the-body-element)

  ---------------------------------------------------------------------------------------------------

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

`body`

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

`alink`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`background`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`bgcolor`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`bottommargin`

1

79

35Before Firefox 35, it was supported in Quirks Mode only.

No

15

≤4

4.4

18

35Before Firefox 35, it was supported in Quirks Mode only.

14

≤3.2

1.0

`leftmargin`

1

79

35Before Firefox 35, it was supported in Quirks Mode only.

No

15

≤4

4.4

18

35Before Firefox 35, it was supported in Quirks Mode only.

14

≤3.2

1.0

`link`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`rightmargin`

1

79

35Before Firefox 35, it was supported in Quirks Mode only.

No

15

≤4

4.4

18

35Before Firefox 35, it was supported in Quirks Mode only.

14

≤3.2

1.0

`text`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`topmargin`

1

79

35Before Firefox 35, it was supported in Quirks Mode only.

No

15

≤4

4.4

18

35Before Firefox 35, it was supported in Quirks Mode only.

14

≤3.2

1.0

`vlink`

1

12

1

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

See also
--------

- [`<html>`](html)
- [`<head>`](head)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body>>

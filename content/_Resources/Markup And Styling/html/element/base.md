\<base\>: The Document Base URL element
=======================================

The `<base>` [HTML](../index) element specifies the base URL to use for
all *relative* URLs in a document. There can be only one `<base>`
element in a document.

A document\'s used base URL can be accessed by scripts with
[`Node.baseURI`](https://developer.mozilla.org/en-US/docs/Web/API/Node/baseURI).
If the document has no `<base>` elements, then `baseURI` defaults to
[`location.href`](https://developer.mozilla.org/en-US/docs/Web/API/Location/href).

  --------------------------------------------- -----------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   Metadata content.
  Permitted content                             None; it is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element).
  Tag omission                                  There must be no closing tag.
  Permitted parents                             A [`<head>`](head) that doesn\'t contain another [`<base>`](base) element.
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          No `role` permitted
  DOM interface                                 [`HTMLBaseElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

**Warning:** If either of the following attributes are specified, this
element **must** come before other elements with attribute values of
URLs, such as [`<link>`](link)\'s `href` attribute.

[`href`](#href)

:   The base URL to be used throughout the document for relative URLs.
    Absolute and relative URLs are allowed.
    [`data:`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URLs)
    and `javascript:` URLs are not allowed.

[`target`](#target)

:   A **keyword** or **author-defined name** of the default [browsing
    context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context)
    to show the results of navigation from [`<a>`](a), [`<area>`](area),
    or [`<form>`](form) elements without explicit `target` attributes.
    The following keywords have special meanings:

    -   `_self` (default): Show the result in the current browsing
        context.
    -   `_blank`: Show the result in a new, unnamed browsing context.
    -   `_parent`: Show the result in the parent browsing context of the
        current one, if the current page is inside a frame. If there is
        no parent, acts the same as `_self`.
    -   `_top`: Show the result in the topmost browsing context (the
        browsing context that is an ancestor of the current one and has
        no parent). If there is no parent, acts the same as `_self`.

Usage notes
-----------

### Multiple \<base\> elements

If multiple `<base>` elements are used, only the first `href` and first
`target` are obeyed --- all others are ignored.

### In-page anchors

Links pointing to a fragment in the document --- e.g.
`<a href="#some-id">` --- are resolved with the `<base>`, triggering an
HTTP request to the base URL with the fragment attached.

For example, given `<base href="https://example.com/">` and this link:
`<a href="#anchor">To anchor</a>`. The link points to
`https://example.com/#anchor`.

### Open Graph

[Open Graph](https://ogp.me/) tags do not acknowledge `<base>`, and
should always have full absolute URLs. For example:

[html]

```html
<meta property="og:image" content="https://example.com/thumbnail.jpg" />
```

Examples
--------

[html]

```html
<base href="https://www.example.com/" />
<base target="_blank" />
<base target="_top" href="https://example.com/" />
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-base-element]](https://html.spec.whatwg.org/multipage/semantics.html#the-base-element)

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

`base`

1

12

1

YesBefore Internet Explorer 7, `<base>` can be positioned anywhere in
the document and the nearest value of `<base>` is used.

15

3

4.4

18

4

14

2

1.0

`href`

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

`target`

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base>>

\<html\>: The HTML Document / Root element
==========================================

The `<html>` [HTML](_Resources/Markup%20And%20Styling/index.md) element represents the root (top-level
element) of an HTML document, so it is also referred to as the *root
element*. All other elements must be descendants of this element.

  ------------------------------------ -------------------------------------------------------------------------------------------------
  [Content                             None.
  categories](../content_categories)

  Permitted content                    One [`<head>`](head) element, followed by one [`<body>`](body) element.

  Tag omission                         The start tag may be omitted if the first thing inside the `<html>` element is not a comment.\
                                       The end tag may be omitted if the `<html>` element is not immediately followed by a comment.

  Permitted parents                    None. This is the root element of a document.

  Implicit ARIA role                   [document](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/document_role)

  Permitted ARIA roles                 No `role` permitted

  DOM interface                        [`HTMLHtmlElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLHtmlElement)
  ------------------------------------ -------------------------------------------------------------------------------------------------

Attributes
----------

This element includes the [global attributes](../global_attributes).

[`manifest`](#manifest) [Deprecated]

:   Specifies the
    [URI](https://developer.mozilla.org/en-US/docs/Glossary/URI) of a
    resource manifest indicating resources that should be cached
    locally.

[`version`](#version) [Deprecated]

:   Specifies the version of the HTML [Document Type
    Definition](https://developer.mozilla.org/en-US/docs/Glossary/Doctype)
    that governs the current document. This attribute is not needed,
    because it is redundant with the version information in the document
    type declaration.

[`xmlns`](#xmlns)

:   Specifies the
    [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML)
    [Namespace](https://developer.mozilla.org/en-US/docs/Glossary/Namespace)
    of the document. Default value is `"http://www.w3.org/1999/xhtml"`.
    This is required in documents parsed with XML
    [parsers](https://developer.mozilla.org/en-US/docs/Glossary/Parser),
    and optional in text/html documents.

Example
-------

[html]

```html
<!doctype html>
<html lang="en">
  <head>
    <!-- … -->
  </head>
  <body>
    <!-- … -->
  </body>
</html>
```

Accessibility concerns
----------------------

While HTML does not require authors to specify `<html>` element start
and ending tags, it is important for authors to do so as it will allow
them to specify the [`lang`](../global_attributes#lang) for the webpage.
Providing a `lang` attribute with a valid language tag according to [RFC
5646: Tags for Identifying Languages (also known as BCP
47)](https://datatracker.ietf.org/doc/html/rfc5646) on the `<html>`
element will help screen reading technology determine the proper
language to announce. The identifying language tag should describe the
language used by the majority of the content of the page. Without it,
screen readers will typically default to the operating system\'s set
language, which may cause mispronunciations.

Including a valid `lang` declaration on the `<html>` element also
ensures that important metadata contained in the page\'s
[`<head>`](head), such as the page\'s [`<title>`](title), are also
announced properly.

- [MDN Understanding WCAG, Guideline 3.1
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Understandable#guideline_3.1_%e2%80%94_readable_make_text_content_readable_and_understandable)
- [Understanding Success Criterion 3.1.1 \| W3C Understanding WCAG
    2.1](https://www.w3.org/WAI/WCAG21/Understanding/language-of-page.html)

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-html-element]](https://html.spec.whatwg.org/multipage/semantics.html#the-html-element)

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

`html`

1

12

1

Yes

≤12.1

1

4.4

18

4

≤12.1

1

1.0

`manifest`

4

12

3.5--84

3Before version 3.5, Firefox ignores the `NETWORK` and `FALLBACK`
sections of the cache manifest file.

10

10.6

4--16.4

4.4

18

4--84

11

3.2--16.4

1.0

`version`

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

`xmlns`

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

See also
--------

- MathML top-level element: `<math>`
- SVG top-level element:
    [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html>>

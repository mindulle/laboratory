\<q\>: The Inline Quotation element
===================================

The `<q>` [HTML](../index) element indicates that the enclosed text is a
short inline quotation. Most modern browsers implement this by
surrounding the text in quotation marks. This element is intended for
short quotations that don\'t require paragraph breaks; for long
quotations use the [`<blockquote>`](blockquote) element.

Try it
------

Attributes
----------

This element includes the [global attributes](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`cite`](#cite)

:   The value of this attribute is a URL that designates a source
    document or message for the information quoted. This attribute is
    intended to point to information explaining the context or the
    reference for the quote.

Examples
--------

[html]

```html
<p>
  According to Mozilla's website,
  <q cite="https://www.mozilla.org/en-US/about/history/details/">
    Firefox 1.0 was released in 2004 and became a big success.
  </q>
</p>
```

### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `generic`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-q-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-q-element)

  ---------------------------------------------------------------------------------------------------------

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

`q`

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

- The [`<blockquote>`](blockquote) element for long quotations.
- The [`<cite>`](cite) element for source citations.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q>>

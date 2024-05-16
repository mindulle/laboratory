\<blockquote\>: The Block Quotation element
===========================================

The `<blockquote>` [HTML](../index) element indicates that the enclosed
text is an extended quotation. Usually, this is rendered visually by
indentation (see [Notes](#usage_notes) for how to change it). A URL for
the source of the quotation may be given using the `cite` attribute,
while a text representation of the source can be given using the
[`<cite>`](cite) element.

Try it
------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`cite`](#cite)

:   A URL that designates a source document or message for the
    information quoted. This attribute is intended to point to
    information explaining the context or the reference for the quote.

Usage notes
-----------

To change the indentation applied to the quoted text, use the
[CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS)
[`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left)
and/or
[`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right)
properties, or the
[`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin)
shorthand property.

To include shorter quotes inline rather than in a separate block, use
the [`<q>`](q) (Quotation) element.

Examples
--------

This example demonstrates the use of the `<blockquote>` element to quote
a passage from [RFC
1149](https://datatracker.ietf.org/doc/html/rfc1149), *A Standard for
the Transmission of IP Datagrams on Avian Carriers*.

[html]

```html
<blockquote cite="https://datatracker.ietf.org/doc/html/rfc1149">
  <p>
    Avian carriers can provide high delay, low throughput, and low altitude
    service. The connection topology is limited to a single point-to-point path
    for each carrier, used with standard carriers, but many carriers can be used
    without significant interference with each other, outside early spring. This
    is because of the 3D ether space available to the carriers, in contrast to
    the 1D ether used by IEEE802.3. The carriers have an intrinsic collision
    avoidance system, which increases availability.
  </p>
</blockquote>
```

### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), sectioning root, palpable content.
  Permitted content                             [Flow content](../content_categories#flow_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content).
  Implicit ARIA role                            `blockquote`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLQuoteElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLQuoteElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-blockquote-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-blockquote-element)

  -----------------------------------------------------------------------------------------------------------------------

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

`blockquote`

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

`cite`

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

- The [`<q>`](q) element for inline quotations.
- The [`<cite>`](cite) element for source citations.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/blockquote>>

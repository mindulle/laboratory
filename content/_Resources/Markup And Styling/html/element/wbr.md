\<wbr\>: The Line Break Opportunity element
===========================================

The `<wbr>` [HTML](../index) element represents a word break
opportunity---a position within text where the browser may optionally
break a line, though its line-breaking rules would not otherwise create
a break at that location.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Notes
-----

On UTF-8 encoded pages, `<wbr>` behaves like the
`U+200B ZERO-WIDTH SPACE` code point. In particular, it behaves like a
Unicode bidi BN code point, meaning it has no effect on
[bidi](https://developer.mozilla.org/en-US/docs/Glossary/BiDi)-ordering:
`<div dir=rtl>123,<wbr>456</div>` displays, when not broken on two
lines, `123,456` and not `456,123`.

For the same reason, the `<wbr>` element does not introduce a hyphen at
the line break point. To make a hyphen appear only at the end of a line,
use the soft hyphen character entity (`&shy;`) instead.

Examples
--------

*[The Yahoo Style
Guide](https://web.archive.org/web/20121014054923/http://styleguide.yahoo.com/)*
recommends [breaking a URL *before*
punctuation](https://web.archive.org/web/20121105171040/http://styleguide.yahoo.com/editing/treat-abbreviations-capitalization-and-titles-consistently/website-names-and-addresses),
to avoid leaving a punctuation mark at the end of the line, which the
reader might mistake for the end of the URL.

[html]

```html
<p>
  http://this<wbr />.is<wbr />.a<wbr />.really<wbr />.long<wbr />.example<wbr />.com/With<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages<wbr />/deeper<wbr />/level<wbr />/pages
</p>
```

### Result

Technical summary
-----------------

  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content).
  Permitted content                             Empty
  Tag omission                                  It is a [void element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element); it must have a start tag, but must not have an end tag.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-wbr-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-wbr-element)

  -------------------------------------------------------------------------------------------------------------

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

`wbr`

1

79

1

5.5--7

11.6

4

4.4

18

4

12

3.2

1.0

See also
--------

- [`overflow-wrap`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)
- [`word-break`](https://developer.mozilla.org/en-US/docs/Web/CSS/word-break)
- [`hyphens`](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens)
- The [`<br>`](br) element

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/wbr>>

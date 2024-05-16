\<dt\>: The Description Term element
====================================

The `<dt>` [HTML](../index) element specifies a term in a description or
definition list, and as such must be used inside a [`<dl>`](dl) element.
It is usually followed by a [`<dd>`](dd) element; however, multiple
`<dt>` elements in a row indicate several terms that are all defined by
the immediate next [`<dd>`](dd) element.

The subsequent [`<dd>`](dd) (**Description Details**) element provides
the definition or other related text associated with the term specified
using `<dt>`.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

For examples, see the [examples provided for the `<dl>`
element](dl#examples).

Technical summary
-----------------

  ------------------------------------ ---------------------------------------------------------------------------------------
  [Content                             None.
  categories](../content_categories)

  Permitted content                    [Flow content](../content_categories#flow_content), but with no [`<header>`](header),
                                       [`<footer>`](footer), sectioning content or heading content descendants.

  Tag omission                         The start tag is required. The end tag may be omitted if this element is immediately
                                       followed by another `<dt>` element or a [`<dd>`](dd) element, or if there is no more
                                       content in the parent element.

  Permitted parents                    A [`<dl>`](dl) or (in
                                       [WHATWG](https://developer.mozilla.org/en-US/docs/Glossary/WHATWG) HTML,
                                       [W3C](https://developer.mozilla.org/en-US/docs/Glossary/W3C) HTML 5.2 and later) a
                                       [`<div>`](div) that is a child of a [`<dl>`](dl).\
                                       This element can be used before a [`<dd>`](dd) or another [`<dt>`](dt) element.

  Implicit ARIA role                   [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)

  Permitted ARIA roles                 `listitem`

  DOM interface                        [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) Up to
                                       Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the
                                       [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement)
                                       interface for this element.
  ------------------------------------ ---------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-dt-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-dt-element)

  -------------------------------------------------------------------------------------------------------

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

`dt`

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

- [`<dl>`](dl)
- [`<dd>`](dd)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dt>>

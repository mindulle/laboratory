\<dd\>: The Description Details element
=======================================

The `<dd>` [HTML](../index) element provides the description,
definition, or value for the preceding term ([`<dt>`](dt)) in a
description list ([`<dl>`](dl)).

Try it
------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`nowrap`](#nowrap) [Non-standard]

:   If the value of this attribute is set to `yes`, the definition text
    will not wrap. The default value is `no`.

Examples
--------

For examples, see the [examples provided for the `<dl>`
element](dl#examples).

Technical summary
-----------------

  ------------------------------------ -------------------------------------------------------------------------------
  [Content                             None.
  categories](../content_categories)

  Permitted content                    [Flow content](../content_categories#flow_content).

  Tag omission                         The start tag is required. The end tag may be omitted if this element is
                                       immediately followed by another `<dd>` element or a [`<dt>`](dt) element, or if
                                       there is no more content in the parent element.

  Permitted parents                    A [`<dl>`](dl) or a [`<div>`](div) that is a child of a [`<dl>`](dl).\
                                       This element can be used after a [`<dt>`](dt) or another [`<dd>`](dd) element.

  Implicit ARIA role                   [No corresponding
                                       role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)

  Permitted ARIA roles                 No `role` permitted

  DOM interface                        [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  ------------------------------------ -------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-dd-element]](https://html.spec.whatwg.org/multipage/grouping-content.html#the-dd-element)

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

`dd`

1

12

1Before Firefox 4, this element was implemented using the
`HTMLSpanElement` interface instead of `HTMLElement`.

Yes

15

≤4

4.4

18

4

14

≤3.2

1.0

`nowrap`

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
- [`<dt>`](dt)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dd>>

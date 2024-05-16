\<bdo\>: The Bidirectional Text Override element
================================================

The `<bdo>` [HTML](../index) element overrides the current
directionality of text, so that the text within is rendered in a
different direction.

Try it
------

The text\'s characters are drawn from the starting point in the given
direction; the individual characters\' orientation is not affected (so
characters don\'t get drawn backward, for example).

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`dir`](#dir)

:   The direction in which text should be rendered in this element\'s
    contents. Possible values are:

    -   `ltr`: Indicates that the text should go in a left-to-right
        direction.
    -   `rtl`: Indicates that the text should go in a right-to-left
        direction.

Examples
--------

[html]

```html
<!-- Switch text direction -->
<p>This text will go left to right.</p>
<p><bdo dir="rtl">This text will go right to left.</bdo></p>
```

### Result

Notes
-----

The HTML 4 specification did not specify events for this element; they
were added in XHTML. This is most likely an oversight.

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `generic`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the `HTMLSpanElement` interface for this element.
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-bdo-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-bdo-element)

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

`bdo`

≤15

12

10

Yes

≤15

≤4

4.4

18

10

14

≤3.2

1.0

See also
--------

- Related HTML element: [`<bdi>`](bdi)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/bdo>>

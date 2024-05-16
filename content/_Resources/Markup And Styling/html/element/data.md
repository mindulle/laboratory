\<data\>: The Data element
==========================

The `<data>` [HTML](../index) element links a given piece of content
with a machine-readable translation. If the content is time- or
date-related, the [`<time>`](time) element must be used.

Try it
------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `generic`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLDataElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLDataElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

[`value`](#value)

:   This attribute specifies the machine-readable translation of the
    content of the element.

Examples
--------

The following example displays product names but also associates each
name with a product number.

[html]

```html
<p>New Products</p>
<ul>
  <li><data value="398">Mini Ketchup</data></li>
  <li><data value="399">Jumbo Ketchup</data></li>
  <li><data value="400">Mega Jumbo Ketchup</data></li>
</ul>
```

### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-data-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-data-element)

  ---------------------------------------------------------------------------------------------------------------

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

`data`

62

≤18

22

No

49

10

62

62

22

46

10

8.0

See also
--------

- The HTML [`<time>`](time) element.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/data>>

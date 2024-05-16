\<address\>: The Contact Address element
========================================

The `<address>` [HTML](../index) element indicates that the enclosed
HTML provides contact information for a person or people, or for an
organization.

Try it
------

The contact information provided by an `<address>` element\'s contents
can take whatever form is appropriate for the context, and may include
any type of contact information that is needed, such as a physical
address, URL, email address, phone number, social media handle,
geographic coordinates, and so forth. The `<address>` element should
include the name of the person, people, or organization to which the
contact information refers.

`<address>` can be used in a variety of contexts, such as providing a
business\'s contact information in the page header, or indicating the
author of an article by including an `<address>` element within the
[`<article>`](article).

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- The `<address>` element can only be used to represent the contact
    information for its nearest [`<article>`](article) or
    [`<body>`](body) element ancestor.
- This element should not contain more information than the contact
    information, like a publication date (which belongs in a
    [`<time>`](time) element).
- Typically an `<address>` element can be placed inside the
    [`<footer>`](footer) element of the current section, if any.

Examples
--------

This example demonstrates the use of `<address>` to demarcate the
contact information for an article\'s author.

[html]

```html
<address>
  You can contact author at
  <a href="http://www.somedomain.com/contact">www.somedomain.com</a>.<br />
  If you see any bugs, please
  <a href="mailto:webmaster@somedomain.com">contact webmaster</a>.<br />
  You may also want to visit us:<br />
  Mozilla Foundation<br />
  331 E Evelyn Ave<br />
  Mountain View, CA 94041<br />
  USA
</address>
```

### Result

Although it renders text with the same default styling as the [`<i>`](i)
or [`<em>`](em) elements, it is more appropriate to use `<address>` when
dealing with contact information, as it conveys additional semantic
information.

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), palpable content.
  Permitted content                             [Flow content](../content_categories#flow_content), but with no nested `<address>` element, no heading content ([`<hgroup>`](hgroup), [h1](heading_elements), [h2](heading_elements), [h3](heading_elements), [h4](heading_elements), [h5](heading_elements), [h6](heading_elements)), no sectioning content ([`<article>`](article), [`<aside>`](aside), [`<section>`](section), [`<nav>`](nav)), and no [`<header>`](header) or [`<footer>`](footer) element.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [flow content](../content_categories#flow_content), but always excluding `<address>` elements (according to the logical principle of symmetry, if `<address>` tag, as a parent, can not have nested `<address>` element, then the same `<address>` content can not have `<address>` tag as its parent).
  Implicit ARIA role                            `group`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) Prior to Gecko 2.0 (Firefox 4), Gecko implemented this element using the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-address-element]](https://html.spec.whatwg.org/multipage/sections.html#the-address-element)

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

`address`

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

- Others section-related elements: [`<body>`](body), [`<nav>`](nav),
    [`<article>`](article), [`<aside>`](aside), [h1](heading_elements),
    [h2](heading_elements), [h3](heading_elements),
    [h4](heading_elements), [h5](heading_elements),
    [h6](heading_elements), [`<hgroup>`](hgroup), [`<footer>`](footer),
    [`<section>`](section), [`<header>`](header);
- [Sections and outlines of an HTML document](heading_elements).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/address>>

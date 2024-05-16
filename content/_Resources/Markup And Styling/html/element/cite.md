\<cite\>: The Citation element
==============================

The `<cite>` [HTML](../index) element is used to mark up the title of a
cited creative work. The reference may be in an abbreviated form
according to context-appropriate conventions related to citation
metadata.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

In the context of the `<cite>` element, a creative work that might be
cited could be, for example, one of the following:

- A book
- A research paper
- An essay
- A poem
- A musical score
- A song
- A play or film script
- A film
- A television show
- A game
- A sculpture
- A painting
- A theatrical production
- A play
- An opera
- A musical
- An exhibition
- A legal case report
- A computer program
- A website
- A web page
- A blog post or comment
- A forum post or comment
- A tweet
- A Facebook post
- A written or oral statement
- And so forth.

To include a reference to the source of quoted material which is
contained within a [`<blockquote>`](blockquote) or [`<q>`](q) element,
use the [`cite`](blockquote#cite) attribute on the element.

Typically, browsers style the contents of a `<cite>` element in italics
by default. To avoid this, apply the CSS
[`font-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-style)
property to the `<cite>` element.

Examples
--------

[html]

```html
<p>More information can be found in <cite>[ISO-0000]</cite>.</p>
```

### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) Up to Gecko 1.9.2 (Firefox 4) inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-cite-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-cite-element)

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

- The element [`<blockquote>`](blockquote) for long quotations.
- The element [`<q>`](q) for inline quotations and the
    [`cite`](q#cite) attribute.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/cite>>

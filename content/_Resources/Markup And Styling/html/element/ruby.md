\<ruby\>: The Ruby Annotation element
=====================================

The `<ruby>` [HTML](../index) element represents small annotations that
are rendered above, below, or next to base text, usually used for
showing the pronunciation of East Asian characters. It can also be used
for annotating other kinds of text, but this usage is less common.

The term *ruby* originated as [a unit of measurement used by
typesetters](https://en.wikipedia.org/wiki/Agate_(typography)),
representing the smallest size that text can be printed on newsprint
while remaining legible.

Try it
------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

### Example 1: Character

[html]

```html
<ruby>
  漢 <rp>(</rp><rt>Kan</rt><rp>)</rp> 字 <rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>
```

#### Result

### Example 2: Word

[html]

```html
<ruby> 明日 <rp>(</rp><rt>Ashita</rt><rp>)</rp> </ruby>
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-ruby-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-ruby-element)

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

`ruby`

5

12

38

5

15

5

4.4

18

38

14

4.2

1.0

See also
--------

- [`<rt>`](rt)
- [`<rp>`](rp)
- [`<rb>`](rb)
- [`<rtc>`](rtc)
- [`text-transform`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform):
    full-size-kana

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby>>

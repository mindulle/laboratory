\<rt\>: The Ruby Text element
=============================

The `<rt>` [HTML](../index) element specifies the ruby text component of
a ruby annotation, which is used to provide pronunciation, translation,
or transliteration information for East Asian typography. The `<rt>`
element must always be contained within a [`<ruby>`](ruby) element.

Try it
------

See the article about the [`<ruby>`](ruby) element for more examples.

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Examples
--------

### Using ruby annotations

This simple example provides Romaji transliteration for the kanji
characters within the [`<ruby>`](ruby) element:

[html]

```html
<ruby> 漢 <rt>Kan</rt> 字 <rt>ji</rt> </ruby>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  The end tag may be omitted if the `<rt>` element is immediately followed by an `<rt>` or [`<rp>`](rp) element, or if there is no more content in the parent element
  Permitted parents                             A [`<ruby>`](ruby) element.
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-rt-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-rt-element)

  -----------------------------------------------------------------------------------------------------------

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

`rt`

5

79

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

- [`<ruby>`](ruby)
- [`<rp>`](rp)
- [`<rb>`](rb)
- [`<rtc>`](rtc)
- [`text-transform: full-size-kana`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt>>

\<rp\>: The Ruby Fallback Parenthesis element
=============================================

The `<rp>` [HTML](../index) element is used to provide fall-back
parentheses for browsers that do not support display of ruby annotations
using the [`<ruby>`](ruby) element. One `<rp>` element should enclose
each of the opening and closing parentheses that wrap the [`<rt>`](rt)
element that contains the annotation\'s text.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Ruby annotations are for showing pronunciation of East Asian
    characters, like using Japanese furigana or Taiwanese bopomofo
    characters. The `<rp>` element is used in the case of lack of
    [`<ruby>`](ruby) element support; the `<rp>` content provides what
    should be displayed in order to indicate the presence of a ruby
    annotation, usually parentheses.

Examples
--------

### Using ruby annotations

This example uses ruby annotations to display the
[Romaji](https://en.wikipedia.org/wiki/Romaji) equivalents for each
character.

[html]

```html
<ruby>
  漢 <rp>(</rp><rt>Kan</rt><rp>)</rp> 字 <rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>
```

#### Result

See the article about the [`<ruby>`](ruby) element for further examples.

### Without ruby support

If your browser does not support ruby annotations, the result looks like
this instead:

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             Text
  Tag omission                                  The end tag can be omitted if the element is immediately followed by an [`<rt>`](rt) or another `<rp>` element, or if there is no more content in the parent element.
  Permitted parents                             A [`<ruby>`](ruby) element. `<rp>` must be positioned immediately before or after an [`<rt>`](rt) element.
  Implicit ARIA role                            [No corresponding role](https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-rp-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-rp-element)

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

`rp`

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
- [`<rt>`](rt)
- [`<rb>`](rb)
- [`<rtc>`](rtc)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rp>>

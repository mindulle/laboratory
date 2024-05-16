\<rb\>: The Ruby Base element
=============================

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<rb>` [HTML](../index) element is used to delimit the base text
component of a [`<ruby>`](ruby) annotation, i.e. the text that is being
annotated. One `<rb>` element should wrap each separate atomic segment
of the base text.

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

- Ruby annotations are for showing pronunciation of East Asian
    characters, like using Japanese furigana or Taiwanese bopomofo
    characters. The `<rb>` element is used to separate out each segment
    of the ruby base text.
- Even though `<rb>` is not a [void
    element](https://developer.mozilla.org/en-US/docs/Glossary/Void_element),
    it is common to just include the opening tag of each element in the
    source code, so that the ruby markup is less complex and easier to
    read. The browser can then fill in the full element in the rendered
    version.
- You need to include one [`<rt>`](rt) element for each base
    segment/`<rb>` element that you want to annotate.

Examples
--------

### Using rb

In this example, we provide an annotation for the original character
equivalent of \"Kanji\":

[html]

```html
<ruby>
  <rb>漢</rb><rb>字 </rb><rp>(</rp><rt>kan</rt><rt>ji</rt><rp>)</rp>
</ruby>
```

Note how we\'ve included two `<rb>` elements, to delimit the two
separate parts of the ruby base text. The annotation on the other hand
is delimited by two [`<rt>`](rt) elements.

#### Result

### Separate annotations

Note that we could also write this example with the two base text parts
annotated completely separately. In this case we don\'t need to include
`<rb>` elements:

[html]

```html
<ruby>
  漢 <rp>(</rp><rt>Kan</rt><rp>)</rp> 字 <rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>
```

#### Result

See the article about the [`<ruby>`](ruby) element for further examples.

Technical summary
-----------------

  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   None.
  Permitted content                             As a child of a [`<ruby>`](ruby) element.
  Tag omission                                  The end tag can be omitted if the element is immediately followed by an [`<rt>`](rt), [`<rtc>`](rtc), or [`<rp>`](rp) element or another `<rb>` element, or if there is no more content in the parent element.
  Permitted parents                             A [`<ruby>`](ruby) element.
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [HTML Standard\
  [\#
  rb]](https://html.spec.whatwg.org/multipage/obsolete.html#rb)

  -----------------------------------------------------------------------

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

`rb`

5Blink has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

79Blink has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

38

5

15Blink has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

5Safari has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

4.4Blink has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

18Blink has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

38

14Blink has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

4.2Safari has support for parsing the `rb` element, but not for
rendering `rb` content as expected.

1.0Blink has support for parsing the `rb` element, but not for rendering
`rb` content as expected.

See also
--------

- [`<ruby>`](ruby)
- [`<rt>`](rt)
- [`<rp>`](rp)
- [`<rtc>`](rtc)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rb>>

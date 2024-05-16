\<sup\>: The Superscript element
================================

The `<sup>` [HTML](../index) element specifies inline text which is to
be displayed as superscript for solely typographical reasons.
Superscripts are usually rendered with a raised baseline using smaller
text.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The `<sup>` element should only be used for typographical reasons---that
is, to change the position of the text to comply with typographical
conventions or standards, rather than solely for presentation or
appearance purposes.

For example, to style the
[wordmark](https://en.wikipedia.org/wiki/Wordmark) of a business or
product which uses a raised baseline should be done using CSS (most
likely
[`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align))
rather than `<sup>`. This would be done using, for example,
`vertical-align: super` or, to shift the baseline up 50%,
`vertical-align: 50%`.

Appropriate use cases for `<sup>` include (but aren\'t necessarily
limited to):

- Displaying exponents, such as \"x ^3^ .\" It may be worth
    considering the use of
    [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) for
    these, especially in more complex cases. See [Exponents](#exponents)
    under [Examples](#examples) below.
- Displaying [superior
    lettering](https://en.wikipedia.org/wiki/Superior_letter), which is
    used in some languages when rendering certain abbreviations. For
    example, in French, the word \"mademoiselle\" can be abbreviated \"M
    ^lle^ \"); this is an acceptable use case. See [Superior
    lettering](#superior_lettering) for examples.
- Representing ordinal numbers, such as \"4 ^th^ \" instead of
    \"fourth.\" See [Ordinal numbers](#ordinal_numbers) for examples.

Examples
--------

### Exponents

Exponents, or powers of a number, are among the most common uses of
superscripted text. For example:

[html]

```html
<p>
  One of the most common equations in all of physics is <var>E</var>=<var>m</var
  ><var>c</var><sup>2</sup>.
</p>
```

#### Result

### Superior lettering

Superior lettering is not technically the same thing as superscript.
However, it is common to use `<sup>` to present superior lettering in
HTML. Among the most common uses of superior lettering is the
presentation of certain abbreviations in French:

[html]

```html
<p>Robert a présenté son rapport à M<sup>lle</sup> Bernard.</p>
```

#### Result

### Ordinal numbers

Ordinal numbers, such as \"fourth\" in English or \"quinto\" in Spanish
may be abbreviated using numerals and language-specific text rendered in
superscript:

[html]

```html
<p>
  The ordinal number "fifth" can be abbreviated in various languages as follows:
</p>
<ul>
  <li>English: 5<sup>th</sup></li>
  <li>French: 5<sup>ème</sup></li>
</ul>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `superscript`
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-sub-and-sup-elements]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-sub-and-sup-elements)

  -------------------------------------------------------------------------------------------------------------------------------

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

`sup`

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

- The [`<sub>`](sub) HTML element that produces subscripts. Note that
    you cannot use `sub` and `sup` at the same time: you need to use
    [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) to
    produce both a superscript and a subscript next to the chemical
    symbol of an element, representing its atomic number and its nuclear
    number.
- The
    [`<msub>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msub),
    [`<msup>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msup),
    and
    [`<msubsup>`](https://developer.mozilla.org/en-US/docs/Web/MathML/Element/msubsup)
    MathML elements.
- The CSS
    [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
    property.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup>>

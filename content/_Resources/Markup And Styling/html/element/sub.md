\<sub\>: The Subscript element
==============================

The `<sub>` [HTML](../index) element specifies inline text which should
be displayed as subscript for solely typographical reasons. Subscripts
are typically rendered with a lowered baseline using smaller text.

Try it
------

Attributes
----------

This element only includes the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

Usage notes
-----------

The `<sub>` element should be used only for typographical reasons---that
is, to change the position of the text to comply with typographical
conventions or standards, rather than solely for presentation or
appearance purposes.

For example, using `<sub>` to style the name of a company which uses
altered baselines in their
[wordmark](https://en.wikipedia.org/wiki/Wordmark) would not be
appropriate; instead, CSS should be used. For example, you could use the
[`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align)
property with a declaration like `vertical-align: sub` or, to more
precisely control the baseline shift, `vertical-align: -25%`.

Appropriate use cases for `<sub>` include (but aren\'t necessarily
limited to):

- Marking up footnote numbers. See [Footnote
    numbers](#footnote_numbers) for an example.
- Marking up the subscript in mathematical variable numbers (although
    you may also consider using a
    [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML)
    formula for this). See [Variable subscripts](#variable_subscripts).
- Denoting the number of atoms of a given element within a chemical
    formula (such as every developer\'s best friend, C ~8~ H ~10~ N ~4~
    O ~2~ , otherwise known as \"caffeine\"). See [Chemical
    formulas](#chemical_formulas).

Examples
--------

### Footnote numbers

Traditional footnotes are denoted using numbers which are rendered in
subscript. This is a common use case for `<sub>`:

[html]

```html
<p>
  According to the computations by Nakamura, Johnson, and Mason<sub>1</sub> this
  will result in the complete annihilation of both particles.
</p>
```

#### Result

### Variable subscripts

In mathematics, families of variables related to the same concept (such
as distances along the same axis) are represented using the same
variable name with a subscript following. For example:

[html]

```html
<p>
  The horizontal coordinates' positions along the X-axis are represented as
  <var>x<sub>1</sub></var> … <var>x<sub>n</sub></var>.
</p>
```

#### Result

### Chemical formulas

When writing a chemical formula, such as H~2~0, the number of atoms of a
given element within the described molecule is represented using a
subscripted number; in the case of water, the subscripted \"2\"
indicates that there are two atoms of hydrogen in the molecule.

Another example:

[html]

```html
<p>
  Almost every developer's favorite molecule is
  C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>, which is commonly known
  as "caffeine."
</p>
```

#### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content).
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            `subscript`
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

`sub`

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

- The [`<sup>`](sup) HTML element that produces superscript. Note that
    you cannot use `sup` and `sub` both at the same time: you need to
    use [MathML](https://developer.mozilla.org/en-US/docs/Web/MathML) to
    produce both a superscript directly above a subscript next to the
    chemical symbol of an element, representing its atomic number and
    its nuclear number.
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
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub>>

\<dfn\>: The Definition element
===============================

The `<dfn>` [HTML](../index) element is used to indicate the term being
defined within the context of a definition phrase or sentence. The
ancestor [`<p>`](p) element, the [`<dt>`](dt)/[`<dd>`](dd) pairing, or
the nearest [`<section>`](section) ancestor of the `<dfn>` element, is
considered to be the definition of the term.

Try it
------

Attributes
----------

This element\'s attributes include the [](_Resources/Markup%20And%20Styling/html/global_attributes/index.md).

The [`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title) attribute has special meaning,
as noted below.

Usage notes
-----------

There are some not-entirely-obvious aspects to using the `<dfn>`
element. We examine those here.

### Specifying the term being defined

The term being defined is identified following these rules:

1. If the `<dfn>` element has a [`title`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#title)
    attribute, the value of the `title` attribute is considered to be
    the term being defined. The element must still have text within it,
    but that text may be an abbreviation (perhaps using
    [`<abbr>`](abbr)) or another form of the term.
2. If the `<dfn>` contains a single child element and does not have any
    text content of its own, and the child element is an
    [`<abbr>`](abbr) element with a `title` attribute itself, then the
    exact value of the `<abbr>` element\'s `title` is the term being
    defined.
3. Otherwise, the text content of the `<dfn>` element is the term being
    defined. This is shown [in the first example
    below](#basic_identification_of_a_term).

**Note:** If the `<dfn>` element has a `title` attribute, it *must*
contain the term being defined and no other text.

### Links to `<dfn>` elements

If you include an [`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) attribute on the
`<dfn>` element, you can then link to it using [`<a>`](a) elements. Such
links should be uses of the term, with the intent being that the reader
can quickly navigate to the term\'s definition if they\'re not already
aware of it, by clicking on the term\'s link.

This is shown in the example under [Links to
definitions](#links_to_definitions) below.

Examples
--------

Let\'s take a look at some examples of various usage scenarios.

### Basic identification of a term

This example uses a plain `<dfn>` element to identify the location of a
term within the definition.

#### HTML

[html]

```html
<p>
  The <strong>HTML Definition element (<dfn>&lt;dfn&gt;</dfn>)</strong> is used
  to indicate the term being defined within the context of a definition phrase
  or sentence.
</p>
```

Since the `<dfn>` element has no `title`, the text contents of the
`<dfn>` element itself are used as the term being defined.

#### Result

### Links to definitions

To add links to the definitions, you create the link the same way you
always do, with the [`<a>`](a) element.

#### HTML

[html]

```html
<p>
  The
  <strong>HTML Definition element (<dfn id="definition-dfn">&lt;dfn&gt;</dfn>)</strong>
  is used to indicate the term being defined within the context of a definition
  phrase or sentence.
</p>

<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. Graece donan, Latine
  voluptatem vocant. Confecta res esset. Duo Reges: constructio interrete.
  Scrupulum, inquam, abeunti;
</p>

<p>
  Because of all of that, we decided to use the
  <code><a href="#definition-dfn">&lt;dfn&gt;</a></code> element for this
  project.
</p>
```

Here we see the definition --- now with an
[`id`](_Resources/Markup%20And%20Styling/html/global_attributes/index.md#id) attribute, `"definition-dfn"`, which can
be used as the target of a link. Later on, a link is created using `<a>`
with the [`href`](a#href) attribute set to `"#definition-dfn"` to set up
the link back to the definition.

#### Result

### Using abbreviations and definitions together

In some cases, you may wish to use an abbreviation for a term when
defining it. This can be done by using the `<dfn>` and [`<abbr>`](abbr)
elements in tandem, like this:

#### HTML

[html]

```html
<p>
  The <dfn><abbr title="Hubble Space Telescope">HST</abbr></dfn> is among the
  most productive scientific instruments ever constructed. It has been in orbit
  for over 20 years, scanning the sky and returning data and photographs of
  unprecedented quality and detail.
</p>

<p>
  Indeed, the <abbr title="Hubble Space Telescope">HST</abbr> has arguably done
  more to advance science than any device ever built.
</p>
```

Note the `<abbr>` element nested inside the `<dfn>`. The former
establishes that the term is an abbreviation (\"HST\") and specifies the
full term (\"Hubble Space Telescope\") in its `title` attribute. The
latter indicates that the abbreviated term represents a term being
defined.

#### Result

Technical summary
-----------------

  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Content categories](../content_categories)   [Flow content](../content_categories#flow_content), [phrasing content](../content_categories#phrasing_content), palpable content.
  Permitted content                             [Phrasing content](../content_categories#phrasing_content), but no [`<dfn>`](dfn) element must be a descendant.
  Tag omission                                  None, both the starting and ending tag are mandatory.
  Permitted parents                             Any element that accepts [phrasing content](../content_categories#phrasing_content).
  Implicit ARIA role                            [`term`](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/term_role)
  Permitted ARIA roles                          Any
  DOM interface                                 [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement)
  --------------------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [HTML Standard\
  [\#
  the-dfn-element]](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-dfn-element)

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

`dfn`

15

12

1

Yes

15

6

4.4

18

4

14

6

1.0

See also
--------

- Elements related to definition lists: [`<dl>`](dl), [`<dt>`](dt),
    [`<dd>`](dd)
- [`<abbr>`](abbr)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dfn>>

:lang()
=======

The `:lang()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-class](pseudo-classes.md) matches elements based on the language
they are determined to be in.

Try it
------

**Note:** In HTML, the language is determined by a combination of the
[`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#lang)
attribute, the
[`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta)
element, and possibly by information from the protocol (such as HTTP
headers). For other document types there may be other document methods
for determining the language.

Syntax
------

### Formal syntax

[css]

```css
:lang(<language-code> [,<language-code> ]*)
  /* ... */
}
```

### Parameters

[`<language-code>`](#language-code)

:   A comma separated list of one or more [`<string>`](string.md)s that
    target an element with a language value according to [BCP
    47](https://tools.ietf.org/html/bcp47) language codes. Matching by
    language range is case-insensitive.

Description
-----------

When selecting languages, there is implicit wildcard matching, so
`:lang(de-DE)` will match `de-DE`, `de-DE-1996`, `de-Latn-DE`,
`de-Latf-DE`, and `de-Latn-DE-1996`. Explicitly using wildcards must
include a full match of a language subtag, so `:lang("*-F*")` is invalid
but `:lang("*-Fr")` is valid.

Examples
--------

### Matching children of a given language

In this example, the `:lang()` pseudo-class is used to match the parents
of quote elements
([`<q>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/q))
using [child combinators](child_combinator.md). Note that this doesn\'t
illustrate the only way to do this, and that the best method to use
depends on the type of document. Also note that
[Unicode](https://developer.mozilla.org/en-US/docs/Glossary/Unicode)
values are used to specify some of the special quote characters.

#### HTML

[html]

```html
<div lang="en">
  <q>This English quote has a <q>nested</q> quote inside.</q>
</div>
<div lang="fr">
  <q>This French quote has a <q>nested</q> quote inside.</q>
</div>
<div lang="de">
  <q>This German quote has a <q>nested</q> quote inside.</q>
</div>
```

#### CSS

[css]

```css
:lang(en) > q {
  quotes: "\201C" "\201D" "\2018" "\2019";
}
:lang(fr) > q {
  quotes: "« " " »";
}
:lang(de) > q {
  quotes: "»" "«" "\2039" "\203A";
}
```

#### Result

### Matching multiple languages

The following example shows how to match multiple languages by providing
a comma-separated list of language codes. It\'s also possible to use a
wildcard to match languages in a given language range.

#### CSS

[css]

```css
/* Matches nl and de */
:lang("nl", "de") {
  color: green;
}

/* Omitting quotes & case-insensitive matching */
:lang(EN, FR) {
  color: blue;
}

/* Wildcard matching a language range */
:lang("*-Latn") {
  color: red;
}
```

#### HTML

[html]

```html
<p lang="nl">Dit is een Nederlandse paragraaf.</p>
<p lang="de">Dies ist ein deutscher Satz.</p>
<p lang="en">This is an English sentence.</p>
<p lang="en-GB">Matching the language range of English.</p>
<p lang="fr">Ceci est un paragraphe français.</p>
<p lang="fr-Latn-FR">Ceci est un paragraphe français en latin.</p>
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------

  [Selectors Level 4\
  [\#
  lang-pseudo]](https://drafts.csswg.org/selectors/#lang-pseudo)

  ------------------------------------------------------------------------

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

`:lang`

1

12

1

8

8

3.1

4.4

18

4

10.1

2

1.0

`argument_list`

No

No

114

No

No

9

No

No

114

No

9

No

`wildcards`

No

No

114

No

No

9

No

No

114

No

9

No

See also
--------

- The [`:dir`](:dir) pseudo-class that matches by directionality of
    text
- HTML
    [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#lang)
    attribute
- HTML
    [`translate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#translate)
    attribute
- [RFC 5646: Tags for Identifying Languages (also known as
    BCP 47)](https://datatracker.ietf.org/doc/html/rfc5646)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/:lang>

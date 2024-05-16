hyphens
=======

The `hyphens` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property specifies how words should be hyphenated when text wraps across
multiple lines. It can prevent hyphenation entirely, hyphenate at
manually-specified points within the text, or let the browser
automatically insert hyphens where appropriate.

Try it
------

**Note:** In the above demo, the string \"An extraordinarily long
English word!\" contains the hidden `&shy;` (soft hyphen) character:
`An extra&shy;ordinarily long English word!`. This character is used to
indicate a potential place to insert a hyphen when `hyphens: manual;` is
specified.

Hyphenation rules are language-specific. In HTML, the language is
determined by the
[`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang)
attribute, and browsers will hyphenate only if this attribute is present
and the appropriate hyphenation dictionary is available. In XML, the
[`xml:lang`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/xml:lang)
attribute must be used.

**Note:** The rules defining how hyphenation is performed are not
explicitly defined by the specification, so the exact hyphenation may
vary from browser to browser.

If supported, [`hyphenate-character`](hyphenate-character.md) may be used
to specify an alternative hyphenation character to use at the end of the
line being broken.

Syntax
------

[css]

```css
/* Keyword values */
hyphens: none;
hyphens: manual;
hyphens: auto;

/* Global values */
hyphens: inherit;
hyphens: initial;
hyphens: revert;
hyphens: revert-layer;
hyphens: unset;
```

The `hyphens` property is specified as a single keyword value chosen
from the list below.

### Values

[`none`](#none)

:   Words are not broken at line breaks, even if characters inside the
    words suggest line break points. Lines will only wrap at whitespace.

[`manual`](#manual)

:   Default value. Words are broken for line-wrapping only where
    characters inside the word suggest line break opportunities. See
    [Suggesting line break
    opportunities](#suggesting_line_break_opportunities) below for
    details.

[`auto`](#auto)

:   The browser is free to automatically break words at appropriate
    hyphenation points, following whatever rules it chooses. However,
    suggested line break opportunities (see [Suggesting line break
    opportunities](#suggesting_line_break_opportunities) below) will
    override automatic break point selection when present.

**Note:** The `auto` setting\'s behavior depends on the language being
properly tagged to select the appropriate hyphenation rules. You must
specify a language using the `lang` HTML attribute to guarantee that
automatic hyphenation is applied in that language.

**Note:** If you apply [`word-break: break-all`](word-break.md#break-all)
then no hyphens are shown, even if the word breaks at a hyphenation
point.

Suggesting line break opportunities
-----------------------------------

There are two Unicode characters used to manually specify potential line
break points within text:

[U+2010 (HYPHEN)](#u2010_hyphen)

:   The \"hard\" hyphen character indicates a visible line break
    opportunity. Even if the line is not actually broken at that point,
    the hyphen is still rendered.

[U+00AD (SHY)](#u00ad_shy)

:   An invisible, \"**s**oft\" **hy**phen. This character is not
    rendered visibly; instead, it marks a place where the browser should
    break the word if hyphenation is necessary. In HTML, use `&shy;` to
    insert a soft hyphen.

**Note:** When the HTML
[`<wbr>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/wbr)
element leads to a line break, no hyphen is added.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `manual`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
hyphens = 
  none    |
  manual  |
  auto    
```

Examples
--------

### Specifying text hyphenation

This example uses three classes, one for each possible configuration of
the `hyphens` property.

#### HTML

[html]

```html
<dl>
  <dt><code>none</code>: no hyphen; overflow if needed</dt>
  <dd lang="en" class="none">An extreme&shy;ly long English word</dd>
  <dt>
    <code>manual</code>: hyphen only at &amp;hyphen; or &amp;shy; (if needed)
  </dt>
  <dd lang="en" class="manual">An extreme&shy;ly long English word</dd>
  <dt><code>auto</code>: hyphens where the algorithm decides (if needed)</dt>
  <dd lang="en" class="auto">An extreme&shy;ly long English word</dd>
</dl>
```

#### CSS

[css]

```css
dd {
  width: 55px;
  border: 1px solid black;
}
dd.none {
  hyphens: none;
}
dd.manual {
  hyphens: manual;
}
dd.auto {
  hyphens: auto;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  hyphens-property]](https://drafts.csswg.org/css-text/#hyphens-property)

  ---------------------------------------------------------------------------------

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

`hyphens`

5513

7979

12--79Only works if the specified language is the same as the language
of the underlying OS.

436

10Only works if the specified language is the same as the language of
the underlying OS.

4215

175.1

554.4

5518

436

4214

174.2

6.01.0

`auto_value`

88

55Only supported on macOS.

88

79Only supported on macOS.

6

No

74

42Only supported on macOS.

5.1

55

55

6

42

4.2

6.0

`language_afrikaans`

No

No

8

No

No

No

No

No

8

No

No

No

`language_bosnian`

No

No

8

No

No

No

No

No

8

No

No

No

`language_bulgarian`

No

No

8

No

No

No

No

No

8

No

No

No

`language_catalan`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_croatian`

No

No

8

No

No

9.1

No

No

8

No

9.3

No

`language_czech`

No

No

No

No

No

9.1

No

No

No

No

9.3

No

`language_danish`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_dutch`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_english`

55

12

6For English, Firefox uses an en-US dictionary

10

44

5.1For English, Safari uses different en-GB and en-US dictionaries.

55

55

6For English, Firefox uses an en-US dictionary

43

5For English, Safari uses different en-GB and en-US dictionaries.

6.0

`language_esperanto`

No

No

8

No

No

No

No

No

8

No

No

No

`language_estonian`

No

No

8

No

No

No

No

No

8

No

No

No

`language_finish`

No

No

8

No

No

9.1

No

No

8

No

9.3

No

`language_french`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_galician`

No

No

9

No

No

No

No

No

9

No

No

No

`language_german_reformed_orthography`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_german_swiss_orthography`

No

No

8

No

No

No

No

No

8

No

No

No

`language_german_traditional_orthography`

No

No

8

No

No

No

No

No

8

No

No

No

`language_hungarian`

No

No

9

No

No

9.1

No

No

9

No

9.3

No

`language_icelandic`

No

No

8

No

No

No

No

No

8

No

No

No

`language_interlingua`

No

No

8

No

No

No

No

No

8

No

No

No

`language_italian`

No

No

9

No

No

5.1

No

No

9

No

5

No

`language_kurmanji`

No

No

8

No

No

No

No

No

8

No

No

No

`language_latin`

No

No

8

No

No

No

No

No

8

No

No

No

`language_lithuanian`

No

No

8

No

No

No

No

No

8

No

No

No

`language_mongolian`

No

No

8

No

No

No

No

No

8

No

No

No

`language_norwegian_nn`

No

No

8

No

No

No

No

No

8

No

5

No

`language_norwegian_no`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_polish`

No

No

31

No

No

9.1

No

No

31

No

9.3

No

`language_portuguese`

No

No

8

No

No

9.1

No

No

8

No

9.3

No

`language_portuguese_brazilian`

No

No

8For Brazilian Portuguese, Firefox uses a Portuguese dictionary.

No

No

No

No

No

8For Brazilian Portuguese, Firefox uses a Portuguese dictionary.

No

No

No

`language_russian`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_slovenian`

No

No

8

No

No

No

No

No

8

No

No

No

`language_spanish`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_swedish`

No

No

8

No

No

5.1

No

No

8

No

5

No

`language_turkish`

No

No

9

No

No

5.1

No

No

9

No

5

No

`language_ukrainian`

No

No

9

No

No

9.1

No

No

9

No

9.3

No

`language_upper_sorbian`

No

No

8

No

No

No

No

No

8

No

No

No

`language_welsh`

No

No

8

No

No

No

No

No

8

No

No

No

See also
--------

- [`content`](content.md)
- [`overflow-wrap`](overflow-wrap.md) (formerly `word-wrap`)
- [`word-break`](word-break.md)
- [](wrapping_breaking_text.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens>

font-variant-caps
=================

The `font-variant-caps`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
controls the use of alternate glyphs for capital letters.

Try it
------

When a given font includes capital letter glyphs of multiple different
sizes, this property selects the most appropriate ones. If petite
capital glyphs are not available, they are rendered using small capital
glyphs. If these are not present, the browser synthesizes them from the
uppercase glyphs.

Fonts sometimes include special glyphs for various caseless characters
(such as punctuation marks) to better match the capitalized characters
around them. However, small capital glyphs are never synthesized for
caseless characters.

### Language-specific rules

This property accounts for language-specific case mapping rules. For
example:

- In Turkic languages, such as Turkish (tr), Azerbaijani (az), Crimean
    Tatar (crh), Volga Tatar (tt), and Bashkir (ba), there are two kinds
    of `i` (one with the dot, one without) and two case pairings:
    `i`/`İ` and `ı`/`I`.
- In German (de), the `ß` may become `ẞ` (U+1E9E) in uppercase.
- In Greek (el), vowels lose their accent when the whole word is in
    uppercase (`ά`/`Α`), except for the disjunctive eta (`ή`/`Ή`). Also,
    diphthongs with an accent on the first vowel lose the accent and
    gain a diacritic on the second vowel (`άι`/`ΑΪ`).

Syntax
------

[css]

```css
/* Keyword values */
font-variant-caps: normal;
font-variant-caps: small-caps;
font-variant-caps: all-small-caps;
font-variant-caps: petite-caps;
font-variant-caps: all-petite-caps;
font-variant-caps: unicase;
font-variant-caps: titling-caps;

/* Global values */
font-variant-caps: inherit;
font-variant-caps: initial;
font-variant-caps: revert;
font-variant-caps: revert-layer;
font-variant-caps: unset;
```

The `font-variant-caps` property is specified using a single keyword
value from the list below. In each case, if the font doesn\'t support
the OpenType value, then it synthesizes the glyphs.

### Values

[`normal`](#normal)

:   Deactivates of the use of alternate glyphs.

[`small-caps`](#small-caps)

:   Enables display of small capitals (OpenType feature: `smcp`).
    Small-caps glyphs typically use the form of uppercase letters but
    are displayed using the same size as lowercase letters.

[`all-small-caps`](#all-small-caps)

:   Enables display of small capitals for both upper and lowercase
    letters (OpenType features: `c2sc`, `smcp`).

[`petite-caps`](#petite-caps)

:   Enables display of petite capitals (OpenType feature: `pcap`).

[`all-petite-caps`](#all-petite-caps)

:   Enables display of petite capitals for both upper and lowercase
    letters (OpenType features: `c2pc`, `pcap`).

[`unicase`](#unicase)

:   Enables display of mixture of small capitals for uppercase letters
    with normal lowercase letters (OpenType feature: `unic`).

[`titling-caps`](#titling-caps)

:   Enables display of titling capitals (OpenType feature: `titl`).
    Uppercase letter glyphs are often designed for use with lowercase
    letters. When used in all uppercase titling sequences they can
    appear too strong. Titling capitals are designed specifically for
    this situation.

Accessibility concerns
----------------------

Large sections of text set with a `font-variant` value of
`all-small-caps` or `all-petite-caps` may be difficult for people with
cognitive concerns such as Dyslexia to read.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [W3C Understanding WCAG
    2.1](https://www.w3.org/TR/WCAG21/#visual-presentation)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-variant-caps = 
  normal           |
  small-caps       |
  all-small-caps   |
  petite-caps      |
  all-petite-caps  |
  unicase          |
  titling-caps     
```

Examples
--------

### Setting the small-caps font variant

#### HTML

[html]

```html
<p class="small-caps">Firefox rocks, small caps!</p>
<p class="normal">Firefox rocks, normal caps!</p>
```

#### CSS

[css]

```css
.small-caps {
  font-variant-caps: small-caps;
  font-style: italic;
}
.normal {
  font-variant-caps: normal;
  font-style: italic;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variant-caps-prop]](https://drafts.csswg.org/css-fonts/#font-variant-caps-prop)

  ----------------------------------------------------------------------------------------------

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

`font-variant-caps`

52

79

34

No

39

9.1

52

52

34

41

9.3

6.0

See also
--------

- [`font-variant`](font-variant.md)
- [`font-variant-alternates`](font-variant-alternates.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-numeric`](font-variant-numeric.md)
- [`font-variant-position`](font-variant-position.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-caps>

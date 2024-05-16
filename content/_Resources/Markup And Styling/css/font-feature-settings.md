font-feature-settings
=====================

The `font-feature-settings` CSS property controls advanced typographic
features in OpenType fonts.

Try it
------

Syntax
------

[css]

```css
/* Use the default settings */
font-feature-settings: normal;

/* Set values for OpenType feature tags */
font-feature-settings: "smcp";
font-feature-settings: "smcp" on;
font-feature-settings: "swsh" 2;
font-feature-settings:
  "smcp",
  "swsh" 2;

/* Global values */
font-feature-settings: inherit;
font-feature-settings: initial;
font-feature-settings: revert;
font-feature-settings: revert-layer;
font-feature-settings: unset;
```

Whenever possible, Web authors should instead use the
[`font-variant`](font-variant.md) shorthand property or an associated
longhand property such as
[`font-variant-ligatures`](font-variant-ligatures.md),
[`font-variant-caps`](font-variant-caps.md),
[`font-variant-east-asian`](font-variant-east-asian.md),
[`font-variant-alternates`](font-variant-alternates.md),
[`font-variant-numeric`](font-variant-numeric.md) or
[`font-variant-position`](font-variant-position.md).

These lead to more effective, predictable, understandable results than
`font-feature-settings`, which is a low-level feature designed to handle
special cases where no other way exists to enable or access an OpenType
font feature. In particular, `font-feature-settings` shouldn\'t be used
to enable small caps.

### Values

This property is specified as either the keyword `normal` or as a
comma-separated list of `<feature-tag-value>` values. When rendering
text, the list of OpenType `<feature-tag-value>` values are passed to
the text layout engine to enable or disable font features.

[`normal`](#normal)

:   Indicates that text is laid out using default font settings. This is
    the default value.

[`<feature-tag-value>`](#feature-tag-value)

:   Represents a space-separated tuple consisting of a tag name and an
    optional value.

    The tag name is always a [`<string>`](string) of four
    [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
    characters. If the tag name has more or fewer characters or if it
    contains characters outside the `U+20` -- `U+7E` code point range,
    the descriptor is invalid.

    The optional value can be a positive integer or the keyword `on` or
    `off`. The keywords `on` and `off` are synonyms for the values `1`
    and `0`, respectively. If no value is set, the default is `1`. For
    non-boolean OpenType features (e.g., [stylistic
    alternates](https://learn.microsoft.com/en-ca/typography/opentype/spec/features_pt#tag-salt)),
    the value implies a particular glyph to be selected; for boolean
    features, the value turns the feature on or off.

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
font-feature-settings = 
  normal                |
  <feature-tag-value>#  
```

Examples
--------

### Enabling various font features

[css]

```css
/* use small-cap alternate glyphs */
.smallcaps {
  font-feature-settings: "smcp" on;
}

/* convert both upper and lowercase to small caps (affects punctuation also) */
.allsmallcaps {
  font-feature-settings: "c2sc", "smcp";
}

/* use zeros with a slash through them to differentiate from "O" */
.nicezero {
  font-feature-settings: "zero";
}

/* enable historical forms */
.hist {
  font-feature-settings: "hist";
}

/* disable common ligatures, usually on by default */
.noligs {
  font-feature-settings: "liga" 0;
}

/* enable tabular (monospaced) figures */
td.tabular {
  font-feature-settings: "tnum";
}

/* enable automatic fractions */
.fractions {
  font-feature-settings: "frac";
}

/* use the second available swash character */
.swash {
  font-feature-settings: "swsh" 2;
}

/* enable stylistic set 7 */
.fancystyle {
  font-family: Gabriola;
  font-feature-settings: "ss07";
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-feature-settings-prop]](https://drafts.csswg.org/css-fonts/#font-feature-settings-prop)

  ------------------------------------------------------------------------------------------------------

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

`font-feature-settings`

4816

15

34The [ISO/IEC CD 14496-22 3rd
edition](https://mpeg.chiariglione.org/standards/mpeg-4/open-font-format/text-isoiec-cd-14496-22-3rd-edition)
suggests using the `ssty` feature to provide glyph variants more
suitable for use in scripts (for example primes used as superscripts).
Starting with Firefox 29, this is done automatically by the
[MathML](https://developer.mozilla.org/docs/Web/MathML) rendering
engine. The ISO/IEC CD 14496-22 3rd edition also suggests applying the
`dtls` feature to letters when placing mathematical accents to get
dotless forms (for example dotless i, j with a hat). Starting with
Firefox 35, this is done automatically by the MathML rendering engine.
You can override the default values determined by the MathML rendering
engine with CSS.

15From Firefox 4 to Firefox 14 (inclusive), Firefox supported an older,
slightly different syntax. See [OpenType Font Feature support in Firefox
4](https://hacks.mozilla.org/2010/11/firefox-4-font-feature-support/).

10

3515

9.1

4.4

48

34The [ISO/IEC CD 14496-22 3rd
edition](https://mpeg.chiariglione.org/standards/mpeg-4/open-font-format/text-isoiec-cd-14496-22-3rd-edition)
suggests using the `ssty` feature to provide glyph variants more
suitable for use in scripts (for example primes used as superscripts).
Starting with Firefox 29, this is done automatically by the
[MathML](https://developer.mozilla.org/docs/Web/MathML) rendering
engine. The ISO/IEC CD 14496-22 3rd edition also suggests applying the
`dtls` feature to letters when placing mathematical accents to get
dotless forms (for example dotless i, j with a hat). Starting with
Firefox 35, this is done automatically by the MathML rendering engine.
You can override the default values determined by the MathML rendering
engine with CSS.

15From Firefox 4 to Firefox 14 (inclusive), Firefox supported an older,
slightly different syntax. See [OpenType Font Feature support in Firefox
4](https://hacks.mozilla.org/2010/11/firefox-4-font-feature-support/).

3514

9.3

5.0

See also
--------

- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`src`](src.md)
- [`unicode-range`](unicode-range.md)
- [OpenType feature
    tags](https://docs.microsoft.com/typography/opentype/spec/featurelist)
    list
- [OpenType features in
    CSS](https://sparanoid.com/lab/opentype-features/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-feature-settings>

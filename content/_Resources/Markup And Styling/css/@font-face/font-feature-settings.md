font-feature-settings
=====================

The `font-feature-settings` CSS descriptor allows you to define the
initial settings to use for the font defined by the
[`@font-face`](@font-face.md) at-rule. You can further use this
descriptor to control typographic font features such as ligatures, small
caps, and swashes, for the font defined by `@font-face`. The values for
this descriptor are the same as the
[`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md) property, except for
the global keyword values.

Since this descriptor sets feature values on the font object in the
`@font-face` at-rule and not on an entire element, only some glyphs in
an element may be rendered using this descriptor.

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
```

### Values

This descriptor is specified as either the keyword `normal` or as a
comma-separated list of `<feature-tag-value>` values. When rendering
text, the list of OpenType `<feature-tag-value>` values are passed to
the text layout engine to enable or disable font features.

[`normal`](#normal)

:   Indicates that text is laid out using default font settings. This is
    the default value.

[`<feature-tag-value>`](#feature-tag-value)

:   Represents a space-separated tuple consisting of a tag name and an
    optional value.

    The tag name is always a [`<string>`](../string) of four
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

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `normal`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```text
font-feature-settings = 
  normal                |
  <feature-tag-value>#  
```

Examples
--------

### Enabling swash glyphs using the \@font-face at-rule

In this example, the tag name `swsh` and a boolean value `1` are used as
the value for the `font-feature-settings` descriptor in the `@font-face`
at-rule.

#### HTML

[html]

```html
<p class="swashoff">Swash is off here</p>
<p class="swashon">Swash is on here</p>
```

#### CSS

[css]

```css
@font-face {
  font-family: MonteCarlo;
  src: url("montecarlo-regular.woff2");
}
@font-face {
  font-family: MonteCarlo2;
  src: url("montecarlo-regular.woff2");
  font-feature-settings: "swsh" 1;
}
p {
  font-size: 3rem;
  margin: 0.7rem 3rem;
}
.swashoff {
  font-family: MonteCarlo;
}
.swashon {
  font-family: MonteCarlo2;
}
```

#### Result

Line 1 shows the default ornate design of the
[MonteCarlo](https://github.com/googlefonts/monte-carlo) font, and line
2 shows the default glyphs being replaced with
[swash](https://learn.microsoft.com/en-ca/typography/opentype/spec/features_pt#tag-swsh)
glyphs.

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-rend-desc]](https://drafts.csswg.org/css-fonts/#font-rend-desc)

  ------------------------------------------------------------------------------

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

No

No

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

No

No

No

No

No

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

No

No

No

See also
--------

- Other `@font-face` descriptors: [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md),
    [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md),
    [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md),
    [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md), [`src`](src.md)
- Related font properties:
    [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md),
    [`font-variant-alternates`](font-variant-alternates.md),
    [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/font-variation-settings.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-feature-settings>

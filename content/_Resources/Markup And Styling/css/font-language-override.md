font-language-override
======================

The `font-language-override` CSS property controls the use of
language-specific glyphs in a typeface.

By default, HTML\'s `lang` attribute tells browsers to display glyphs
designed specifically for that language. For example, a lot of fonts
have a special character for the digraph `fi` that merge the dot on the
\"i\" with the \"f.\" However, if the language is set to Turkish the
typeface will likely know not to use the merged glyph; Turkish has two
versions of the \"i,\" one with a dot (`i`) and one without (`ı`), and
using the ligature would incorrectly transform a dotted \"i\" into a
dotless \"i.\"

The `font-language-override` property lets you override the typeface
behavior for a specific language. This is useful, for example, when the
typeface you\'re using lacks proper support for the language. For
instance, if a typeface doesn\'t have proper rules for the Azeri
language, you can force the font to use Turkish glyphs, which follow
similar rules.

Syntax
------

[css]

```css
/* Keyword value */
font-language-override: normal;

/* <string> values */
font-language-override: "ENG"; /* Use English glyphs */
font-language-override: "TRK"; /* Use Turkish glyphs */

/* Global values */
font-language-override: inherit;
font-language-override: initial;
font-language-override: revert;
font-language-override: revert-layer;
font-language-override: unset;
```

The `font-language-override` property is specified as the keyword
`normal` or a `<string>`.

### Values

[`normal`](#normal)

:   Tells the browser to use font glyphs that are appropriate for the
    language specified by the `lang` attribute. This is the default
    value.

[`<string>`](string.md)

:   Tells the browser to use font glyphs that are appropriate for the
    language specified by the string. The string must match a language
    tag found in the [OpenType language
    system](https://docs.microsoft.com/typography/opentype/spec/languagetags).
    For example, \"ENG\" is English, and \"KOR\" is Korean.

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
font-language-override = 
  normal    |
  <string>  
```

Examples
--------

### Using Danish glyphs

#### HTML

[html]

```html
<p class="para1">Default language setting.</p>
<p class="para2">
  This is a string with the <code>font-language-override</code> set to Danish.
</p>
```

#### CSS

[css]

```css
p.para1 {
  font-language-override: normal;
}

p.para2 {
  font-language-override: "DAN";
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-language-override-prop]](https://drafts.csswg.org/css-fonts/#font-language-override-prop)

  --------------------------------------------------------------------------------------------------------

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

`font-language-override`

No

No

344

No

No

No

No

No

344

No

No

No

See also
--------

- [`font-variant`](font-variant.md),
    [`font-variant-position`](font-variant-position.md),
    [`font-variant-east-asian`](font-variant-east-asian.md),
    [`font-variant-caps`](font-variant-caps.md),
    [`font-variant-ligatures`](font-variant-ligatures.md),
    [`font-variant-numeric`](font-variant-numeric.md),
    [`font-variant-alternates`](font-variant-alternates.md),
    [`font-synthesis`](font-synthesis.md), [`font-kerning`](font-kerning.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-language-override>

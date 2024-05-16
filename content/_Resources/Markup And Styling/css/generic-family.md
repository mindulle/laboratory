\<generic-family\>
==================

The `<generic-family>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents the keyword values for generic font families
used in the [`font`](font.md) shorthand and [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
longhand properties. The `<generic-family>` represents one or more
locally-installed fonts belonging to that category of fonts.

Syntax
------

[css]

```css
<generic-family> = serif | sans-serif | monospace | cursive | fantasy | system-ui |
   ui-serif | ui-sans-serif | ui-monospace | ui-rounded | emoji | math | fangsong
```

Values
------

The `<generic-family>`
[enumerated](https://developer.mozilla.org/en-US/docs/Glossary/Enumerated)
type is specified using one of the values listed below:

[`serif`](#serif)

:   A serif is a small line or stroke attached to the end of a larger
    stroke in a letter. In serif fonts, glyphs have finishing strokes,
    flared or tapering ends. Examples include Lucida Bright, Lucida Fax,
    Palatino, Palatino Linotype, Palladio, and URW Palladio.

[`sans-serif`](#sans-serif)

:   A font without serifs; glyphs have plain stroke endings, without
    ornamentation. Example sans-serif fonts include Open Sans, Fira
    Sans, Lucida Sans, Lucida Sans Unicode, Trebuchet MS, Liberation
    Sans, and Nimbus Sans L.

[`monospace`](#monospace)

:   All glyphs have the same fixed width. Example monospace fonts
    include Fira Mono, DejaVu Sans Mono, Menlo, Consolas, Liberation
    Mono, Monaco, and Lucida Console.

[`cursive`](#cursive)

:   Glyphs in cursive fonts generally have either joining strokes or
    other cursive characteristics beyond those of italic typefaces. The
    glyphs are partially or completely connected, and the result looks
    more like handwritten pen or brush writing than printed letter work.
    Example cursive fonts include Brush Script MT, Brush Script Std,
    Lucida Calligraphy, Lucida Handwriting, and Apple Chancery.

[`fantasy`](#fantasy)

:   Fantasy fonts are primarily decorative fonts that contain playful
    representations of characters. Example fantasy fonts include
    Papyrus, Herculanum, Party LET, Curlz MT, and Harrington.

[`system-ui`](#system-ui)

:   Glyphs are taken from the default user interface font on a given
    platform. Because typographic traditions vary widely across the
    world, this generic family is provided for typefaces that don\'t map
    cleanly into the others.

[`ui-serif`](#ui-serif)

:   The default user interface serif font. See the definition of `serif`
    above.

[`ui-sans-serif`](#ui-sans-serif)

:   The default user interface sans-serif font. See the definition of
    `sans-serif` above.

[`ui-monospace`](#ui-monospace)

:   The default user interface monospace font. See the definition of
    `monospace` above.

[`ui-rounded`](#ui-rounded)

:   The default user interface font that has rounded features.

[`math`](#math)

:   Fonts for displaying mathematical expressions, for example
    superscript and subscript, brackets that cross several lines,
    nesting expressions, and double-struck glyphs with distinct
    meanings.

[`emoji`](#emoji)

:   Fonts that are specifically designed to render emoji.

[`fangsong`](#fangsong)

:   A particular style of Chinese characters that are between
    serif-style Song and cursive-style Kai forms. This style is often
    used for government documents.

Examples
--------

This example demos several of the `<generic-family>` enumerated values
for the [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md) property.

### HTML

[html]

```html
<ul>
  <li class="serif">serif</li>
  <li class="sans-serif">sans-serif</li>
  <li class="monospace">monospace</li>
  <li class="cursive">cursive</li>
  <li class="fantasy">fantasy</li>
  <li class="system-ui">system-ui</li>
</ul>
```

### CSS

[css]

```css
ul {
  font-size: 1.5rem;
  line-height: 2;
}
.serif {
  font-family: serif;
}
.sans-serif {
  font-family: sans-serif;
}
.monospace {
  font-family: monospace;
}
.cursive {
  font-family: cursive;
}
.fantasy {
  font-family: fantasy;
}
.system-ui {
  font-family: system-ui;
}
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  generic-font-families]](https://drafts.csswg.org/css-fonts/#generic-font-families)

  --------------------------------------------------------------------------------------------

See also
--------

- Properties that use this data type: [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md) and
    [`font`](font.md)
- [CSS fonts module](css_fonts.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/generic-family>

font-family
===========

The `font-family` CSS property specifies a prioritized list of one or
more font family names and/or generic family names for the selected
element.

Try it
------

Values are separated by commas to indicate that they are alternatives.
The browser will select the first font in the list that is installed or
that can be downloaded using a [`@font-face`](@font-face.md) at-rule.

It is often convenient to use the shorthand property [`font`](font.md) to
set `font-size` and other font related properties all at once.

You should always include at least one generic family name in a
`font-family` list, since there\'s no guarantee that any given font is
available. This lets the browser select an acceptable fallback font when
necessary.

The `font-family` property specifies a list of fonts, from highest
priority to lowest. Font selection *does not* stop at the first font in
the list that is on the user\'s system. Rather, font selection is done
*one character at a time*, so that if an available font does not have a
glyph for a needed character, the latter fonts are tried. When a font is
only available in some [styles](_Resources/Markup%20And%20Styling/css/font-style.md), [variants](font-variant.md),
or [sizes](font-size.md), those properties may also influence which font
family is chosen.

Syntax
------

[css]

```css
/* A font family name and a generic family name */
font-family: "Gill Sans Extrabold", sans-serif;
font-family: "Goudy Bookletter 1911", sans-serif;

/* A generic family name only */
font-family: serif;
font-family: sans-serif;
font-family: monospace;
font-family: cursive;
font-family: fantasy;
font-family: system-ui;
font-family: ui-serif;
font-family: ui-sans-serif;
font-family: ui-monospace;
font-family: ui-rounded;
font-family: emoji;
font-family: math;
font-family: fangsong;

/* Global values */
font-family: inherit;
font-family: initial;
font-family: revert;
font-family: revert-layer;
font-family: unset;
```

The `font-family` property lists one or more font families, separated by
commas. Each font family is specified as either a `<family-name>` or a
`<generic-name>` value.

The example below lists two font families, the first with a
`<family-name>` and the second with a `<generic-name>`:

[css]

```css
font-family: "Gill Sans Extrabold", sans-serif;
```

### Values

[`<family-name>`](#family-name)

:   The name of a font family. For example, \"Times\" and \"Helvetica\"
    are font families. Font family names containing whitespace should be
    quoted. For example: \"Comic Sans MS\".

[`<generic-name>`](#generic-name)

:   Generic font families are a fallback mechanism, a means of
    preserving some of the style sheet author\'s intent when none of the
    specified fonts are available. Generic family names are keywords and
    must not be quoted. A generic font family should be the last item in
    the list of font family names. The following keywords are defined:

    [`serif`](#serif)

    :   Glyphs have finishing strokes, flared or tapering ends, or have
        actual serifed endings.

        For example: Lucida Bright, Lucida Fax, Palatino, Palatino
        Linotype, Palladio, URW Palladio, serif.

    [`sans-serif`](#sans-serif)

    :   Glyphs have stroke endings that are plain.

        For example: Open Sans, Fira Sans, Lucida Sans, Lucida Sans
        Unicode, Trebuchet MS, Liberation Sans, Nimbus Sans L,
        sans-serif.

    [`monospace`](#monospace)

    :   All glyphs have the same fixed width.

        For example: Fira Mono, DejaVu Sans Mono, Menlo, Consolas,
        Liberation Mono, Monaco, Lucida Console, monospace.

    [`cursive`](#cursive)

    :   Glyphs in cursive fonts generally have either joining strokes or
        other cursive characteristics beyond those of italic typefaces.
        The glyphs are partially or completely connected, and the result
        looks more like handwritten pen or brush writing than printed
        letter work.

        For example: Brush Script MT, Brush Script Std, Lucida
        Calligraphy, Lucida Handwriting, Apple Chancery, cursive.

    [`fantasy`](#fantasy)

    :   Fantasy fonts are primarily decorative fonts that contain
        playful representations of characters.

        For example: Papyrus, Herculanum, Party LET, Curlz MT,
        Harrington, fantasy.

    [`system-ui`](#system-ui)

    :   Glyphs are taken from the default user interface font on a given
        platform. Because typographic traditions vary widely across the
        world, this generic is provided for typefaces that don\'t map
        cleanly into the other generics.

    [`ui-serif`](#ui-serif)

    :   The default user interface serif font.

    [`ui-sans-serif`](#ui-sans-serif)

    :   The default user interface sans-serif font.

    [`ui-monospace`](#ui-monospace)

    :   The default user interface monospace font.

    [`ui-rounded`](#ui-rounded)

    :   The default user interface font that has rounded features.

    [`math`](#math)

    :   This is for the particular stylistic concerns of representing
        mathematics: superscript and subscript, brackets that cross
        several lines, nesting expressions, and double struck glyphs
        with distinct meanings.

    [`emoji`](#emoji)

    :   Fonts that are specifically designed to render emoji.

    [`fangsong`](#fangsong)

    :   A particular style of Chinese characters that are between
        serif-style Song and cursive-style Kai forms. This style is
        often used for government documents.

### Valid family names

Font family names must either be given quoted as strings, or unquoted as
a sequence of one or more identifiers. This means that punctuation
characters and digits at the start of each token must be escaped in
unquoted font family names.

It is a **good practice** to quote font family names that contain white
space, digits, or punctuation characters other than hyphens.

For example, the following declarations are valid:

[css]

```css
font-family: "Goudy Bookletter 1911", sans-serif;
```

The following declarations are **invalid**:

[css]

```css
font-family: Goudy Bookletter 1911, sans-serif;
font-family: Red/Black, sans-serif;
font-family: "Lucida" Grande, sans-serif;
font-family: Ahem!, sans-serif;
font-family: test@foo, sans-serif;
font-family: #POUND, sans-serif;
font-family: Hawaii 5-0, sans-serif;
```

The following example is technically **valid** but is not recommended:

[css]

```css
font-family:
  Gill Sans Extrabold,
  sans-serif;
```

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     depends on user agent
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-family = 
  [ <family-name> | <generic-family> ]#  
```

Examples
--------

### Some common font families

[css]

```css
.serif {
  font-family: Times, "Times New Roman", Georgia, serif;
}

.sansserif {
  font-family: Verdana, Arial, Helvetica, sans-serif;
}

.monospace {
  font-family: "Lucida Console", Courier, monospace;
}

.cursive {
  font-family: cursive;
}

.fantasy {
  font-family: fantasy;
}

.emoji {
  font-family: emoji;
}

.math {
  font-family: math;
}

.fangsong {
  font-family: fangsong;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  generic-font-families]](https://drafts.csswg.org/css-fonts/#generic-font-families)

[CSS Fonts Module Level 4\
  [\# font-family-prop]](https://drafts.csswg.org/css-fonts/#font-family-prop)
  --------------------------------------------------------------------------------------------

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

`font-family`

1

12

1Not supported on `option` elements. See [bug
1536148](https://bugzil.la/1536148).

3

3.5

1

4.4

18

4

10.1

1

1.0

`math`

109

109

No

No

95

No

109

109

No

74

No

21.0

`system-ui`

56

79

92

43Supported on macOS only.

No

43

119

56

56

92

43

119

6.0

See also
--------

- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [Fundamental text and font
    styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-family>

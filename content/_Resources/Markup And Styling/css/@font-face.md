\@font-face
===========

The `@font-face` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) specifies a custom font with which to display text;
the font can be loaded from either a remote server or a
locally-installed font on the user\'s own computer.

Syntax
------

[css]

```css
@font-face {
  font-family: "Trickster";
  src:
    local("Trickster"),
    url("trickster-COLRv1.otf") format("opentype") tech(color-COLRv1),
    url("trickster-outline.otf") format("opentype"),
    url("trickster-outline.woff") format("woff");
}
```

### Descriptors

[`ascent-override`](ascent-override.md)

:   Defines the ascent metric for the font.

[`descent-override`](descent-override.md)

:   Defines the descent metric for the font.

[`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)

:   Determines how a font face is displayed based on whether and when it
    is downloaded and ready to use.

[`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)

:   Specifies a name that will be used as the font face value for font
    properties.

[`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)

:   A [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md) value. Accepts two values to
    specify a range that is supported by a font-face, for example
    `font-stretch: 50% 200%;`

[`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)

:   A [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md) value. Accepts two values to specify a
    range that is supported by a font-face, for example
    `font-style: oblique 20deg 50deg;`

[`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)

:   A [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md) value. Accepts two values to specify
    a range that is supported by a font-face, for example
    `font-weight: 100 400;`

    **Note:** The font-variant descriptor was removed from the
    specification in 2018. The [`font-variant`](font-variant) value
    property is supported, but there is no descriptor equivalent.

[`font-feature-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-feature-settings.md)

:   Allows control over advanced typographic features in OpenType fonts.

[`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)

:   Allows low-level control over OpenType or TrueType font variations,
    by specifying the four letter axis names of the features to vary,
    along with their variation values.

[`line-gap-override`](line-gap-override.md)

:   Defines the line gap metric for the font.

[`size-adjust`](size-adjust.md)

:   Defines a multiplier for glyph outlines and metrics associated with
    this font. This makes it easier to harmonize the designs of various
    fonts when rendered at the same font size.

[`src`](src.md)

:   Specifies references to font resources including hints about the
    font format and technology. It is required for the \@font-face rule
    to be valid.

[`unicode-range`](unicode-range.md)

:   The range of Unicode code points to be used from the font.

Description
-----------

It\'s common to use both `url()` and `local()` together, so that the
user\'s installed copy of the font is used if available, falling back to
downloading a copy of the font if it\'s not found on the user\'s device.

If the `local()` function is provided, specifying a font name to look
for on the user\'s device, and if the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
finds a match, that local font is used. Otherwise, the font resource
specified using the `url()` function is downloaded and used.

Browsers attempt to load resources in their list declaration order, so
usually `local()` should be written before `url()`. Both functions are
optional, so a rule block containing only one or more `local()` without
`url()` is possible. If a more specific fonts with `format()` or
`tech()` values are desired, these should be listed *before* versions
that don\'t have these values, as the less-specific variant would
otherwise be tried and used first.

By allowing authors to provide their own fonts, `@font-face` makes it
possible to design content without being limited to the so-called
\"web-safe\" fonts (that is, the fonts which are so common that they\'re
considered to be universally available). The ability to specify the name
of a locally-installed font to look for and use makes it possible to
customize the font beyond the basics while making it possible to do so
without relying on an internet connection.

**Note:** Fallback strategies for loading fonts on older browsers are
described in the [](src.md#fallbacks_for_older_browsers).

The `@font-face` at-rule may be used not only at the top level of a CSS,
but also inside any [](at-rule.md#conditional_group_rules).

### Font MIME Types

  Format                   MIME type
  ------------------------ --------------
  TrueType                 `font/ttf`
  OpenType                 `font/otf`
  Web Open Font Format     `font/woff`
  Web Open Font Format 2   `font/woff2`

### Notes

- Web fonts are subject to the same domain restriction (font files
    must be on the same domain as the page using them), unless [HTTP
    access
    controls](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
    are used to relax this restriction.
- `@font-face` cannot be declared within a CSS selector. For example,
    the following will not work:

    [css]

    ```css
    .className {
      @font-face {
        font-family: "MyHelvetica";
        src: local("Helvetica Neue Bold"), local("HelveticaNeue-Bold"),
          url("MgOpenModernaBold.ttf");
        font-weight: bold;
      }
    }
    ```

Formal syntax
-------------

```
@font-face = 
  @font-face   
```

Examples
--------

### Specifying a downloadable font

This example specifies a downloadable font to use, applying it to the
entire body of the document:

[html]

```html
<!doctype html>
<html lang="en-US">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Web Font Sample</title>
    <style media="screen, print">
      @font-face {
        font-family: "Bitstream Vera Serif Bold";
        src: url("https://mdn.github.io/css-examples/web-fonts/VeraSeBd.ttf");
      }

      body {
        font-family: "Bitstream Vera Serif Bold", serif;
      }
    </style>
  </head>
  <body>
    This is Bitstream Vera Serif Bold.
  </body>
</html>
```

The output of this example code looks like so:

### Specifying local font alternatives

In this example, the user\'s local copy of \"Helvetica Neue Bold\" is
used; if the user does not have that font installed (both the full font
name and the Postscript name are tried), then the downloadable font
named \"MgOpenModernaBold.ttf\" is used instead:

[css]

```css
@font-face {
  font-family: "MyHelvetica";
  src: local("Helvetica Neue Bold"), local("HelveticaNeue-Bold"),
    url("MgOpenModernaBold.ttf");
  font-weight: bold;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-face-rule]](https://drafts.csswg.org/css-fonts/#font-face-rule)

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

`OpenType_CBDT_CBLC`

66

79

No

No

53

No

66

66

No

47

No

9.0

`OpenType_COLRv0`

53

79

31

No

40

11.1

53

53

31

41

11.3

6.0

`OpenType_COLRv1`

98

98

105

No

84

No

98

98

No

68

No

18.0

`OpenType_SBIX`

66

79

No

No

53

9.1

66

66

No

47

9.3

9.0

`OpenType_SVG`

No

No

31

No

No

12.1

No

No

31

No

12.2

No

`SVG_fonts`

1--38

No

No

No

15--25

3.1

≤37--38

18--38

No

14--25

3

1.0--3.0

`WOFF`

6

12

3.5

9

11.1

5.1

4.4

18

4

11.1

5

1.0

`WOFF_2`

36

14

39

No

23

10Supported only on macOS 10.12 (Sierra) and later.

37

36

39

24

10

3.0

`@font-face`

1

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

`ascent-override`

87

87

89

No

73

No

87

87

89

62

No

14.0

`descent-override`

87

87

89

No

73

No

87

87

89

62

No

14.0

`font-display`

60

79

58

No

47

11.1

60

60

58

44

11.3

11.0

`font-family`

4

12

3.5

6

10

3.1

2.2

18

4

10.1

2

1.0

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

`font-stretch`

62

17

62

No

49

10.1

62

62

62

41

10.3

6.0

`font-style`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

`font-variant`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

`font-variation-settings`

No

No

62

No

No

No

No

No

62

No

No

No

`font-weight`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

`line-gap-override`

87

87

89

No

73

No

87

87

89

62

No

14.0

`size-adjust`

92

92

92

No

78

17

92

92

92

No

17

16.0

`src`

4

12

3.5

6

10

3.1

2.2

18

4

10.1

2

1.0

`unicode-range`

1

12

36

9

15

3.1

≤37

18

36

14

3

1.0

See also
--------

- [About
    WOFF](https://developer.mozilla.org/en-US/docs/Web/Guide/WOFF)
- [FontSquirrel \@font-face
    generator](https://www.fontsquirrel.com/tools/webfont-generator)
- [Beautiful fonts with
    \@font-face](https://hacks.mozilla.org/2009/06/beautiful-fonts-with-font-face/)
- [Font Library](https://fontlibrary.org/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face>

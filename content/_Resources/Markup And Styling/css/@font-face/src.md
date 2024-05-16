src
===

The `src` CSS descriptor for the [`@font-face`](@font-face.md) at-rule
specifies the resource containing font data. It is required for the
`@font-face` rule to be valid.

Syntax
------

[css]

```css
/* <url> values */
src: url(https://somewebsite.com/path/to/font.woff); /* Absolute URL */
src: url(path/to/font.woff); /* Relative URL */
src: url("path/to/font.woff"); /* Quoted URL */
src: url(path/to/svgFont.svg#example); /* Fragment identifying font */

/* <font-face-name> values */
src: local(font); /* Unquoted name */
src: local(some font); /* Name containing space */
src: local("font"); /* Quoted name */
src: local("some font"); /* Quoted name containing a space */

/* <tech(<font-tech>)> values */
src: url(path/to/fontCOLRv1.otf) tech(color-COLRv1);
src: url(path/to/fontCOLR-svg.otf) tech(color-SVG);

/* <format(<font-format>)> values */
src: url(path/to/font.woff) format("woff");
src: url(path/to/font.otf) format("opentype");

/* Multiple resources */
src:
  url(path/to/font.woff) format("woff"),
  url(path/to/font.otf) format("opentype");

/* Multiple resources with font format and technologies */
src:
  url("trickster-COLRv1.otf") format(opentype) tech(color-COLRv1),
  url("trickster-outline.otf") format(opentype);
```

### Values

[`url()`](#url)

:   Specifies an external reference consisting of a [`<url>()`](url.md),
    followed by optional hints using the `format()` and `tech()`
    component values that specify the format and font technology of the
    resource referenced by the URL. The `format()` and `tech()`
    components are a comma-separated list of strings of known [font
    formats](#font_formats) and technologies. If a user agent doesn\'t
    support the font technology or formats, it skips downloading the
    font resource. If no format or technology hints are supplied, the
    font resource is always downloaded.

[`format()`](#format)

:   An optional declaration that follows the `url()` value that provides
    a hint for the user agent on the font format. If the value is not
    supported or invalid, the browser may not download the resource,
    potentially saving bandwidth. If omitted, the browser will download
    the resource and then detect the format. If including a font source
    for backward-compatibility that is not in the list of [defined
    keywords](#formal-syntax), enclose the format string in quotes.
    Possible values are described in the [Font formats](#font_formats)
    section below.

[`tech()`](#tech) [Experimental]

:   An optional declaration that follows the `url()` value that provides
    a hint for the user agent on the font technology. The value for
    `tech()` may be one of the keywords described in [Font
    technologies](#font-technologies).

#### local(font-face-name)

:   Specifies the font name should the font be available on the user\'s
    device. Enclosing the font name in quotes is optional.

    **Note:** For OpenType and TrueType fonts, `<font-face-name>` is
    used to match either the Postscript name or the full font name in
    the name table of locally available fonts. Which type of name is
    used varies by platform and font, so you should include both of
    these names to assure proper matching across platforms. Platform
    substitutions for a given font name must not be used.
    

    
    **Note:** Locally available fonts may have been preinstalled on the
    user\'s device, or may have been actively installed by the user.

    While the set of preinstalled fonts is likely to be the same for all
    users of a particular device, the set of user-installed fonts is
    not. By discovering the set of user-installed fonts, a site can
    therefore build a
    [fingerprint](https://developer.mozilla.org/en-US/docs/Glossary/Fingerprinting)
    for the device, helping the site to track users across the web.

    To prevent this, user agents may ignore user-installed fonts when
    using `local()`.

[`<font-face-name>`](#font-face-name)

:   Specifies the full name or postscript name of a locally-installed
    font face using the `local()` component value, which uniquely
    identifies a single font face within a larger family. The name can
    optionally be enclosed in quotes. The font face name [is not
    case-sensitive](https://drafts.csswg.org/css-fonts-3/#font-family-casing).

**Note:** The [Local Font Access
API](https://developer.mozilla.org/en-US/docs/Web/API/Local_Font_Access_API)
can be used to access the user\'s locally installed font data --- this
includes higher-level details such as names, styles, and families, as
well as the raw bytes of the underlying font files.

Description
-----------

The value of this descriptor is a prioritized, comma-separated list of
external references or locally-installed font face names, where each
resource is specified using `url()` or `local()`. When a font is needed,
the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
iterates over the set of references listed using the first one it can
successfully activate. Fonts containing invalid data or local font faces
that are not found are ignored and the user agent loads the next font in
the list.

If multiple `src` descriptors are set, only the last declared rule that
is able to load a resource is applied. If the last `src` descriptor can
load a resource and doesn\'t include a `local()` font, the browser may
download external font files and ignore the local version even if there
is one available on the device.

**Note:** Values within descriptors that the browser considers invalid
are ignored. Some browsers will ignore the whole descriptor if any item
is invalid, even if only one item is invalid. This may affect design of
fallbacks. See [Browser compatibility](#browser_compatibility) for more
information.

As with other URLs in CSS, the URL may be relative, in which case it is
resolved relative to the location of the style sheet containing the
`@font-face` rule. In the case of SVG fonts, the URL points to an
element within a document containing SVG font definitions. If the
element reference is omitted, a reference to the first defined font is
implied. Similarly, font container formats that can contain more than
one font load only one of the fonts for a given `@font-face` rule.
Fragment identifiers are used to indicate which font to load. If a
container format lacks a defined fragment identifier scheme, a simple
1-based indexing scheme (e.g., \"font-collection\#1\" for the first
font, \"font-collection\#2\" for the second font, etc.) is used.

If the font file is a container for multiple fonts, a fragment
identifier is included to indicate the sub-font that should be used, as
shown below:

[css]

```css
/* WhichFont is the PostScript name of a font in the font file */
src: url(collection.otc#WhichFont);
/* WhichFont is the element id of a font in the SVG Font file */
src: url(fonts.svg#WhichFont);
```

### Font formats

The following table shows the valid font keywords and their
corresponding font formats. To check if a font format is supported by a
browser within CSS, use the [`@supports`](@supports.md) rule.

  Keyword               Font Format             Common extensions
  --------------------- ----------------------- -------------------
  `collection`          OpenType Collection     .otc, .ttc
  `embedded-opentype`   Embedded OpenType       .eot
  `opentype`            OpenType                .otf, .ttf
  `svg`                 SVG Font (deprecated)   .svg, .svgz
  `truetype`            TrueType                .ttf
  `woff`                WOFF 1.0                .woff
  `woff2`               WOFF 2.0                .woff2

**Note:**

- `format(svg)` stands for [SVG
    fonts](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/SVG_fonts),
    and `tech(color-SVG)` stands for [OpenType fonts with SVG
    table](https://learn.microsoft.com/en-us/typography/opentype/spec/svg)
    (also called OpenType-SVG color fonts), which are completely
    different.
- The `opentype` and `truetype` values are equivalent whether the font
    file uses cubic bezier curves (within CFF/CFF2 table) or quadratic
    bezier curves (within glyph table).

Older non-normalized `format()` values have the following equivalent
syntax; provided as a string enclosed in quotes for
backward-compatibility reasons:

  Old syntax                        Equivalent syntax
  --------------------------------- -------------------------------------
  `format("woff2-variations")`      `format(woff2) tech(variations)`
  `format("woff-variations")`       `format(woff) tech(variations)`
  `format("opentype-variations")`   `format(opentype) tech(variations)`
  `format("truetype-variations")`   `format(truetype) tech(variations)`

### Font technologies

The following table shows valid values for the `tech()` descriptor and
their corresponding font technologies. To check if a font technology is
supported by a browser within CSS, use the [`@supports`](@supports.md)
at-rule.

  Keyword               Description
  --------------------- -----------------------------------------------------------------------------------------------
  `color-cbdt`          Color bitmap data tables
  `color-colrv0`        Multi-colored glyphs via COLR version 0 table
  `color-colrv1`        Multi-colored glyphs via COLR version 1 table
  `color-sbix`          Standard bitmap graphics tables
  `color-svg`           SVG multi-colored tables
  `features-aat`        TrueType `morx` and `kerx` tables
  `features-graphite`   Graphite features, namely `Silf`, `Glat` , `Gloc` , `Feat`, and `Sill` tables
  `features-opentype`   OpenType `GSUB` and `GPOS` tables
  `incremental`         Incremental font loading
  `palettes`            Font palettes by means of `font-palette` to select one of many color palettes in the font
  `variations`          Font variations in TrueType and OpenType fonts to control the font axis, weight, glyphs, etc.

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `n/a (required)`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```
<url> [ format( <font-format> ) ]? [ tech( <font-tech># ) ]?  |
local( <family-name> )

<font-format> = [ <string> | collection | embedded-opentype | opentype | svg | truetype | woff | woff2 ]

<font-tech> = [ <font-features-tech> | <color-font-tech> | variations | palettes | incremental-patch | incremental-range | incremental-auto ]

<font-features-tech> = [ features-opentype | features-aat | features-graphite ]

<color-font-tech> = [ color-COLRv0 | color-COLRv1 | color-SVG | color-sbix | color-CBDT ]
```

Examples
--------

### Specifying font resources using url() and local()

The example below shows how to define two font faces with the same font
family. The `font-family` is named `MainText`. The first font face has a
regular font, and the second one is a bold version of the same font
family.

[css]

```css
/* Defining a regular font face */
@font-face {
  font-family: MainText;
  src: local(Futura-Medium),
    url('FuturaMedium.woff') format("woff"),
    url('FuturaMedium.otf') format("opentype");
    format("opentype");
}

/* Defining a different bold font face for the same family */
@font-face {
  font-family: MainText;
  src: local(Gill Sans Bold), /* full font name */
    local(GillSans-Bold), /* postscript name */
    url('GillSansBold.woff') format("woff"),
    url('GillSansBold.otf') format("opentype"),
    url("GillSansBold.svg#MyFontBold"); /* Referencing an SVG font fragment by id */
  font-weight: bold;
}

/* Using the regular font face */
p {
  font-family: MainText;
}

/* Font-family is inherited, but bold fonts are used */
p.bold {
  font-weight: bold;
}
```

### Specifying font resources using tech() and format() values

The following example shows how to use the `tech()` and `format()`
values to specify font resources. A font using `color-colrv1` technology
and `opentype` format is specified using the `tech()` and `format()`
values. A color font will be activated if the user agent supports it,
and an `opentype` non-color is provided as a fallback.

[css]

```css
@font-face {
  font-family: "Trickster";
  src:
    url("trickster-COLRv1.otf") format(opentype) tech(color-COLRv1),
    url("trickster-outline.otf") format(opentype);
}

/* Using the font face */
p {
  font-family: "Trickster";
}
```

### Specifying fallbacks for older browsers

Browsers should use a `@font-face` with a single `src` descriptor
listing possible sources for the font. Since the browser will use the
first resource that it is able to load, items should be specified in the
order of your preference for their usage.

Generally this means that local files should appear before remote files
and that resources with `format()` or `tech()` constraints should appear
before resources that don\'t have them (otherwise the less-constrained
version would always be selected). For example:

[css]

```css
@font-face {
  font-family: "MgOpenModernaBold";
  src:
    url("MgOpenModernaBoldIncr.otf") format("opentype") tech(incremental),
    url("MgOpenModernaBold.otf") format(opentype);
}
```

A browser that does not support `tech()` above should ignore the first
item and attempt to load the second resource.

Some browsers do not yet [ignore invalid items](#browser_compatibility),
and instead fail the whole `src` descriptor if any value is invalid. If
working with these browsers you can specify multiple `src` descriptors
as fallbacks. Note that multiple `src` descriptors are attempted in
reverse-order, so at the end we have our normal descriptor with all the
items.

[css]

```css
@font-face {
  font-family: "MgOpenModernaBold";
  src: url("MgOpenModernaBold.otf") format(opentype);
  src: url("MgOpenModernaBoldIncr.otf") format("opentype") tech(incremental);
  src:
    url("MgOpenModernaBoldIncr.otf") format("opentype") tech(incremental),
    url("MgOpenModernaBold.otf") format(opentype);
}
```

### Checking if the user agent supports a font

The following example shows how to check if the user agent supports a
font technology using the [`@supports`](@supports.md) rule. The block of
CSS inside `@supports` will be applied if the user agent supports
`color-COLRv1` technology.

[css]

```css
@supports font-tech(color-COLRv1) {
  @font-face {
    font-family: "Trickster";
    src: url("trickster-COLRv1.otf") format(opentype) tech(color-COLRv1);
  }

  .colored_text {
    font-family: "Trickster";
  }
}
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\# src-desc]](https://drafts.csswg.org/css-fonts/#src-desc)

  -----------------------------------------------------------------------

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

`drop_invalid_item`

108Chrome drops invalid item for `tech()` but not other invalid values

108Edge drops invalid item for `tech()` but not other invalid values

109

No

94Opera drops invalid item for `tech()` but not other invalid values

No

108Chrome drops invalid item for `tech()` but not other invalid values

108Chrome drops invalid item for `tech()` but not other invalid values

109

73Opera drops invalid item for `tech()` but not other invalid values

No

21.0Samsung Internet drops invalid item for `tech()` but not other
invalid values

`format_keyword`

No

No

No

No

No

4

No

No

No

No

5

No

`format_variations`

66

17

62

No

53

11

66

66

62

47

11

9.0

`tech_keyword`

No

No

105preview

No

No

17

No

No

No

No

17

No

See also
--------

- [`@font-face`](@font-face.md)
- [`@supports`](@supports.md)
- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`unicode-range`](unicode-range.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/src>

\@media
=======

The `@media` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) can be used to apply part of a style sheet based on
the result of one or more [](using_media_queries.md). With it, you specify a
media query and a block of CSS to apply to the document if and only if
the media query matches the device on which the content is being used.

**Note:** In JavaScript, the rules created using `@media` can be
accessed with the
[`CSSMediaRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule)
CSS object model interface.

Try it
------

Syntax
------

The `@media` at-rule may be placed at the top level of your code or
nested inside any other [](at-rule.md#conditional_group_rules).

[css]

```css
/* At the top level of your code */
@media screen and (min-width: 900px) {
  article {
    padding: 1rem 3rem;
  }
}

/* Nested within another conditional at-rule */
@supports (display: flex) {
  @media screen and (min-width: 900px) {
    article {
      display: flex;
    }
  }
}
```

For a discussion of media query syntax, please see [](using_media_queries.md#syntax).

Description
-----------

### Media types

*Media types* describe the general category of a device. Except when
using the `not` or `only` logical operators, the media type is optional
and the `all` type is implied.

[`all`](#all)

:   Suitable for all devices.

[`print`](#print)

:   Intended for paged material and documents viewed on a screen in
    print preview mode. (Please see [paged media](css_paged_media.md) for
    information about formatting issues that are specific to these
    formats.)

[`screen`](#screen)

:   Intended primarily for screens.

**Note:** CSS2.1 and [Media Queries
3](https://drafts.csswg.org/mediaqueries-3/#background) defined several
additional media types (`tty`, `tv`, `projection`, `handheld`,
`braille`, `embossed`, and `aural`), but they were deprecated in [Media
Queries 4](https://drafts.csswg.org/mediaqueries/#media-types) and
shouldn\'t be used.

### Media features

*Media features* describe specific characteristics of the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent),
output device, or environment. Media feature expressions test for their
presence or value, and are entirely optional. Each media feature
expression must be surrounded by parentheses.

[`any-hover`](any-hover.md)

:   Does any available input mechanism allow the user to hover over
    elements? Added in Media Queries Level 4.

[`any-pointer`](any-pointer.md)

:   Is any available input mechanism a pointing device, and if so, how
    accurate is it? Added in Media Queries Level 4.

[`aspect-ratio`](_Resources/Markup%20And%20Styling/css/@media/aspect-ratio.md)

:   Width-to-height aspect ratio of the viewport

[`color`](_Resources/Markup%20And%20Styling/css/@media/color.md)

:   Number of bits per color component of the output device, or zero if
    the device isn\'t color

[`color-gamut`](color-gamut.md)

:   Approximate range of colors that are supported by the user agent and
    output device. Added in Media Queries Level 4.

[`color-index`](color-index.md)

:   Number of entries in the output device\'s color lookup table, or
    zero if the device does not use such a table

[`device-aspect-ratio`](device-aspect-ratio.md) [Deprecated]

:   Width-to-height aspect ratio of the output device. Deprecated in
    Media Queries Level 4.

[`device-height`](device-height.md) [Deprecated]

:   Height of the rendering surface of the output device. Deprecated in
    Media Queries Level 4.

[`device-width`](device-width.md) [Deprecated]

:   Width of the rendering surface of the output device. Deprecated in
    Media Queries Level 4.

[`display-mode`](display-mode.md)

:   The display mode of the application, as specified in the web app
    manifest\'s
    [`display`](https://developer.mozilla.org/en-US/docs/Web/Manifest#display)
    member. Defined in the [Web App Manifest
    spec](https://w3c.github.io/manifest/#the-display-mode-media-feature).

[`dynamic-range`](dynamic-range.md)

:   Combination of brightness, contrast ratio, and color depth that are
    supported by the user agent and the output device. Added in Media
    Queries Level 5.

[`forced-colors`](forced-colors.md)

:   Detect whether user agent restricts color palette. Added in Media
    Queries Level 5.

[`grid`](_Resources/Markup%20And%20Styling/css/@media/grid.md)

:   Does the device use a grid or bitmap screen?

[`height`](_Resources/Markup%20And%20Styling/css/@media/height.md)

:   Height of the viewport.

[`hover`](hover.md)

:   Does the primary input mechanism allow the user to hover over
    elements? Added in Media Queries Level 4.

[`inverted-colors`](inverted-colors.md)

:   Is the user agent or underlying OS inverting colors? Added in Media
    Queries Level 5.

[`monochrome`](monochrome.md)

:   Bits per pixel in the output device\'s monochrome frame buffer, or
    zero if the device isn\'t monochrome.

[`orientation`](orientation.md)

:   Orientation of the viewport.

[`overflow-block`](_Resources/Markup%20And%20Styling/css/@media/overflow-block.md)

:   How does the output device handle content that overflows the
    viewport along the block axis? Added in Media Queries Level 4.

[`overflow-inline`](_Resources/Markup%20And%20Styling/css/@media/overflow-inline.md)

:   Can content that overflows the viewport along the inline axis be
    scrolled? Added in Media Queries Level 4.

[`pointer`](pointer.md)

:   Is the primary input mechanism a pointing device, and if so, how
    accurate is it? Added in Media Queries Level 4.

[`prefers-color-scheme`](prefers-color-scheme.md)

:   Detect if the user prefers a light or dark color scheme. Added in
    Media Queries Level 5.

[`prefers-contrast`](prefers-contrast.md)

:   Detects if the user has requested the system increase or decrease
    the amount of contrast between adjacent colors. Added in Media
    Queries Level 5.

[`prefers-reduced-motion`](prefers-reduced-motion.md)

:   The user prefers less motion on the page. Added in Media Queries
    Level 5.

[`resolution`](_Resources/Markup%20And%20Styling/css/@media/resolution.md)

:   Pixel density of the output device.

[`scripting`](scripting.md)

:   Detects whether scripting (i.e. JavaScript) is available. Added in
    Media Queries Level 5.

[`update`](update.md)

:   How frequently the output device can modify the appearance of
    content. Added in Media Queries Level 4.

[`video-dynamic-range`](video-dynamic-range.md)

:   Combination of brightness, contrast ratio, and color depth that are
    supported by the video plane of user agent and the output device.
    Added in Media Queries Level 5.

[`width`](_Resources/Markup%20And%20Styling/css/@media/width.md)

:   Width of the viewport including width of scrollbar.

### Logical operators

The *logical operators* `not`, `and`, `only`, and `or` can be used to
compose a complex media query. You can also combine multiple media
queries into a single rule by separating them with commas.

[`and`](#and)

:   Used for combining multiple media features together into a single
    media query, requiring each chained feature to return `true` for the
    query to be `true`. It is also used for joining media features with
    media types.

[`not`](#not)

:   Used to negate a media query, returning `true` if the query would
    otherwise return `false`. If present in a comma-separated list of
    queries, it will only negate the specific query to which it is
    applied. If you use the `not` operator, you *must also* specify a
    media type.

    **Note:** In Level 3, the `not` keyword can\'t be used to negate an
    individual media feature expression, only an entire media query.

[`only`](#only)

:   Applies a style only if an entire query matches. It is useful for
    preventing older browsers from applying selected styles. When not
    using `only`, older browsers would interpret the query
    `screen and (max-width: 500px)` as `screen`, ignoring the remainder
    of the query, and applying its styles on all screens. If you use the
    `only` operator, you *must also* specify a media type.

[`,`](#sect33) (comma)

:   Commas are used to combine multiple media queries into a single
    rule. Each query in a comma-separated list is treated separately
    from the others Thus, if any of the queries in a list is `true`, the
    entire media statement returns `true`. In other words, lists behave
    like a logical `or` operator.

[`or`](#or)

:   Equivalent to the `,` operator. Added in Media Queries Level 4.

### User agent client hints

Some media queries have corresponding [user agent client
hints](https://developer.mozilla.org/en-US/docs/Web/HTTP/Client_hints).
These are HTTP headers that request content that is pre-optimized for
the particular media requirement. They include
[`Sec-CH-Prefers-Color-Scheme`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-Prefers-Color-Scheme)
and
[`Sec-CH-Prefers-Reduced-Motion`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-Prefers-Reduced-Motion).

Accessibility concerns
----------------------

To best accommodate people who adjust a site\'s text size, use
[`em`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numeric_values)s
when you need a [`<length>`](length.md) for your [](using_media_queries.md).

Both
[`em`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numeric_values)
and
[`px`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numeric_values)
are valid units, but
[`em`](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units#numeric_values)
works better if the user changes the browser text size.

Also consider media queries or [HTTP user agent client
hints](https://developer.mozilla.org/en-US/docs/Web/HTTP/Client_hints#user-agent_client_hints)
to improve the user\'s experience. For example, the media query
[`prefers-reduced-motion`](prefers-reduced-motion.md) or the
eqivalent HTTP header
[`Sec-CH-Prefers-Reduced-Motion`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-Prefers-Reduced-Motion))
can be used to minimize the amount of animation or motion used based on
user preferences.

Security
--------

Because media queries provide insights into the capabilities---and by
extension, the features and design---of the device the user is working
with, there is the potential that they could be abused to construct a
[\"fingerprint\"](https://developer.mozilla.org/en-US/docs/Glossary/Fingerprinting)
which identifies the device, or at least categorizes it to some degree
of detail that may be undesirable to users.

Because of this potential, a browser may opt to fudge the returned
values in some manner in order to prevent them from being used to
precisely identify a computer. A browser might also offer additional
measures in this area; for example, if Firefox\'s \"Resist
Fingerprinting\" setting is enabled, many media queries report default
values rather than values representing the actual device state.

Formal syntax
-------------

```
@media = 
  @media <media-query-list>   
```

Examples
--------

### Testing for print and screen media types

[css]

```css
@media print {
  body {
    font-size: 10pt;
  }
}

@media screen {
  body {
    font-size: 13px;
  }
}

@media screen, print {
  body {
    line-height: 1.2;
  }
}

@media only screen and (min-width: 320px) and (max-width: 480px) and (resolution: 150dpi) {
  body {
    line-height: 1.4;
  }
}
```

Introduced in Media Queries Level 4 is a new range syntax that allows
for less verbose media queries when testing for any feature accepting a
range, as shown in the below examples:

[css]

```css
@media (height > 600px) {
  body {
    line-height: 1.4;
  }
}

@media (400px <= width <= 700px) {
  body {
    line-height: 1.4;
  }
}
```

For more examples, please see [](using_media_queries.md).

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [Media Queries Level 4\
  [\#
  media-descriptor-table]](https://drafts.csswg.org/mediaqueries/#media-descriptor-table)

[CSS Conditional Rules Module Level 3\
  [\# at-media]](https://drafts.csswg.org/css-conditional-3/#at-media)
  -------------------------------------------------------------------------------------------------

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

`-moz-device-pixel-ratio`

No

No

4

No

No

No

No

No

4

No

No

No

`-webkit-animation`

2--36

No

No

No

15--23

4

2--37

18--36

No

14--24

3.2

1.0--3.0

`-webkit-device-pixel-ratio`

1

12

63Implemented as an alias for `-moz-device-pixel-ratio`.

No

15

3

≤37

18

63Implemented as an alias for `-moz-device-pixel-ratio`.

14

1

1.0

`-webkit-max-device-pixel-ratio`

1

12

63Implemented as an alias for `max--moz-device-pixel-ratio`.

No

15

3

≤37

18

63Implemented as an alias for `max--moz-device-pixel-ratio`.

14

1

1.0

`-webkit-min-device-pixel-ratio`

1

12

63Implemented as an alias for `min--moz-device-pixel-ratio`.

No

15

3

≤37

18

63Implemented as an alias for `min--moz-device-pixel-ratio`.

14

1

1.0

`-webkit-transform-2d`

2--36

No

No

No

15--23

4

2--37

18--36

No

14--24

3.2

1.0--3.0

`-webkit-transform-3d`

2

12

49

No

15

4

4.4

18

49

14

3.2

1.0

`-webkit-transition`

2--36

No

No

No

15--23

4

2--37

18--36

No

14--24

3.2

1.0--3.0

`@media`

1

12

1

6

9.2

3

≤37

18

4

10.1

1

1.0

`any-hover`

41

16

64

No

28

9

41

41

64

28

9

5.0

`any-pointer`

41

12

64

No

28

9

41

41

64

28

9

4.0

`aspect-ratio`

3

12

3.5

9

10

5

≤37

18

4

10.1

4.2

1.0

`calc`

66

79

59

No

53

12

66

66

59

47

12

9.0

`color`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`color-gamut`

58

79

110

No

45

10

58

58

110

43

10

7.0

`color-index`

29

79

No

No

16

8

4.4

29

No

16

8

2.0

`device-aspect-ratio`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`device-height`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`device-width`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`display-mode`

42

79

47Firefox 47 and later support `display-mode` values `fullscreen` and
`browser`. Firefox 57 added support for `minimal-ui` and `standalone`
values.

No

29

13

42

42

47Only supports the `browser` value, which always reports `true`.

29

12.2

4.0

`dynamic-range`

98

98

100

No

84

13.1

98

98

100

68

13.4

18.0

`forced-colors`

89

79

89

No

75

16

89

89

89

63

16

15.0

`grid`

1

12

2

10

10

3

≤37

18

4

10.1

1

1.0

`height`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

`hover`

38Before Chrome 41, the implementation was buggy and reported
`(hover: none)` on non-touch-based computers with a mouse/trackpad. See
[bug 441613](https://crbug.com/441613).

12

64

No

28

9

38Before Chrome 41, the implementation was buggy and reported
`(hover: none)` on non-touch-based computers with a mouse/trackpad. See
[bug 441613](https://crbug.com/441613).

50

64

28

9

5.0

`inverted-colors`

No

No

114

No

No

9.1

No

No

No

No

10

No

`media_features`

1

12

1

9

9.2

3

4.4

18

4

10.1

1

1.0

`media_query_values`

66

79

59

No

53

No

66

66

59

47

No

9.0

`monochrome`

1

79

2

No

10

3

≤37

18

4

10.1

1

1.0

`nested-queries`

26

12

11

No

12.1

7

4.4

26

14

12.1

7

1.5

`or_syntax`

104

104

64

No

90

16.4

104

104

64

71

16.4

20.0

`orientation`

3

12

2

9

10.6

5

≤37

18

4

11

4.2

1.0

`overflow-block`

113

113

66

No

99

17

113

113

66

No

17

No

`overflow-inline`

113

113

66

No

99

17

113

113

66

No

17

No

`pointer`

41

12

64

No

28

9

41

50

64

28

9

5.0

`prefers-color-scheme`

76

79

67

No

62

12.1

76

76

67

54

13

14.2

`prefers-contrast`

96

96

101

No

82

14.1

96

96

101

No

14.5

17.0

`prefers-reduced-data`

85

85

No

No

71

No

No

85

No

No

No

No

`prefers-reduced-motion`

74

79

63

No

62

10.1

74

74

64

53

10.3

11.0

`prefers-reduced-transparency`

118

118

113

No

104

No

118

118

No

No

No

No

`range_syntax`

104

104

102

63Only supports range notations where the feature name comes before any
value `(width > 500px)`

No

90

16.4

104

104

102

63Only supports range notations where the feature name comes before any
value `(width > 500px)`

71

16.4

20.0

`resolution`

29

12

8

3.5Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

9

1610--15

16

4.4

29

8

4Supports
[`<integer>`](https://developer.mozilla.org/docs/Web/CSS/integer) values
only.

1610.1--14

16

2.0

`scripting`

120

120

113

No

No

17

No

No

113

No

17

No

`update`

113

113

102

No

99

17

113

113

102

No

17

No

`video-dynamic-range`

98

98

100

No

84

No

No

98

100

No

No

No

`width`

1

12

2

9

10

3

≤37

18

4

10.1

1

1.0

See also
--------

- [Using media queries](using_media_queries.md)
- In JavaScript, `@media` can be accessed via the CSS object model
    interface
    [`CSSMediaRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule).
- [Extended Mozilla media
    features](https://developer.mozilla.org/en-US/docs/Web/CSS/Mozilla_Extensions#media_features)
- [Extended WebKit media
    features](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions#media_features)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@media>

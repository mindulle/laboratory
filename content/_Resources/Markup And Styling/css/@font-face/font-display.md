font-display
============

The `font-display` descriptor for the [`@font-face`](@font-face.md)
at-rule determines how a font face is displayed based on whether and
when it is downloaded and ready to use.

Syntax
------

[css]

```css
/* Keyword values */
font-display: auto;
font-display: block;
font-display: swap;
font-display: fallback;
font-display: optional;
```

### Values

[`auto`](#auto)

:   The font display strategy is defined by the user agent.

[`block`](#block)

:   Gives the font face a short block period and an infinite swap
    period.

[`swap`](#swap)

:   Gives the font face an extremely small block period and an infinite
    swap period.

[`fallback`](#fallback)

:   Gives the font face an extremely small block period and a short swap
    period.

[`optional`](#optional)

:   Gives the font face an extremely small block period and no swap
    period.

**Note:** In Firefox, the preferences
`gfx.downloadable_fonts.fallback_delay` and
`gfx.downloadable_fonts.fallback_delay_short` provide the duration of
the \"short\" and \"extremely small\" periods, respectively.

Description
-----------

The font display timeline is based on a timer that begins the moment the
user agent attempts to use a given downloaded font face. The timeline is
divided into the three periods below which dictate the rendering
behavior of any elements using the font face:

- Font block period: If the font face is not loaded, any element
    attempting to use it must render an *invisible* fallback font face.
    If the font face successfully loads during this period, it is used
    normally.
- Font swap period: If the font face is not loaded, any element
    attempting to use it must render a fallback font face. If the font
    face successfully loads during this period, it is used normally.
- Font failure period: If the font face is not loaded, the user agent
    treats it as a failed load causing normal font fallback.

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `auto`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```text
font-display = 
  auto      |
  block     |
  swap      |
  fallback  |
  optional  
```

Examples
--------

### Specifying fallback font-display

[css]

```css
@font-face {
  font-family: ExampleFont;
  src:
    url(/path/to/fonts/examplefont.woff) format("woff"),
    url(/path/to/fonts/examplefont.eot) format("eot");
  font-weight: 400;
  font-style: normal;
  font-display: fallback;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-display-desc]](https://drafts.csswg.org/css-fonts/#font-display-desc)

  ------------------------------------------------------------------------------------

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

See also
--------

- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`src`](src.md)
- [`unicode-range`](unicode-range.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-display>

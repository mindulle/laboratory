font-stretch
============

The `font-stretch` CSS descriptor allows authors to specify a normal,
condensed, or expanded face for the fonts specified in the
[`@font-face`](@font-face.md) at-rule.

For a particular font family, authors can download various font faces
which correspond to the different styles of the same font family, and
then use the `font-stretch` descriptor to explicitly specify the font
face\'s stretch. The values for the CSS descriptor is same as that of
its corresponding font property.

Syntax
------

[css]

```css
/* Single values */
font-stretch: ultra-condensed;
font-stretch: extra-condensed;
font-stretch: condensed;
font-stretch: semi-condensed;
font-stretch: normal;
font-stretch: semi-expanded;
font-stretch: expanded;
font-stretch: extra-expanded;
font-stretch: ultra-expanded;
font-stretch: 50%;
font-stretch: 100%;
font-stretch: 200%;

/* multiple values */
font-stretch: 75% 125%;
font-stretch: condensed ultra-condensed;
```

The `font-stretch` property is described using any one of the values
listed below.

### Values

[`normal`](#normal)

:   Specifies a normal font face.

[`semi-condensed`](#semi-condensed), `condensed`, `extra-condensed`, `ultra-condensed`

:   Specifies a more condensed font face than normal, with
    ultra-condensed as the most condensed.

[`semi-expanded`](#semi-expanded), `expanded`, `extra-expanded`, `ultra-expanded`

:   Specifies a more expanded font face than normal, with ultra-expanded
    as the most expanded.

[`<percentage>`](#percentage)

:   A [`<percentage>`](percentage.md) value between 50% and 200%
    (inclusive). Negative values are not allowed for this property.

In earlier versions of the `font-stretch` specification, the property
accepts only the nine keyword values. CSS Fonts Level 4 extends the
syntax to accept a `<percentage>` value as well. This enables variable
fonts to offer something more like a continuum of character widths. For
TrueType or OpenType variable fonts, the \"wdth\" variation is used to
implement varying widths.

If the font does not provide a face that exactly matches the given
value, then values less than 100% map to a narrower face, and values
greater than or equal to 100% map to a wider face.

### Keyword to numeric mapping

The table below shows the mapping between keyword values and numeric
percentages:

  Keyword             Percentage
  ------------------- ------------
  `ultra-condensed`   50%
  `extra-condensed`   62.5%
  `condensed`         75%
  `semi-condensed`    87.5%
  `normal`            100%
  `semi-expanded`     112.5%
  `expanded`          125%
  `extra-expanded`    150%
  `ultra-expanded`    200%

### Variable fonts

Most fonts have a particular width which corresponds to one of the
keyterm values. However some fonts, called variable fonts, can support a
range of stretching with more or less fine granularity, and this can
give the designer a much closer degree of control over the chosen
weight. For this, percentage ranges are useful.

For TrueType or OpenType variable fonts, the \"wdth\" variation is used
to implement varying glyph widths.

Accessibility concerns
----------------------

People with dyslexia and other cognitive conditions may have difficulty
reading fonts that are too condensed, especially if the font has a [](_Resources/Markup%20And%20Styling/css/color.md#accessibility_concerns).

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `normal`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```
font-stretch = 
  auto                   |
  <'font-stretch'>  
```

Examples
--------

### Setting a percentage range for font-stretch

The following find a local Open Sans font or import it, and allow using
the font for normal, semi-condensed and semi-expanded states.

[css]

```css
@font-face {
  font-family: "Open Sans";
  src:
    local("Open Sans") format("woff2"),
    url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
  font-stretch: 87.5% 112.5%;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-prop-desc]](https://drafts.csswg.org/css-fonts/#font-prop-desc)

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

See also
--------

- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`src`](src.md)
- [`unicode-range descriptor`](unicode-range.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-stretch>

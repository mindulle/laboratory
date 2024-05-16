font-size-adjust
================

The `font-size-adjust`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
provides a way to modify the size of lowercase letters relative to the
size of uppercase letters, which defines the overall
[`font-size`](font-size.md). This property is useful for situations where
font fallback can occur.

Legibility can become an issue when the first-choice
[`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md) is unavailable and its replacement fallback
font has a significantly different aspect value (height of lowercase
letters divided by font size). Legibility of fonts, especially at small
font sizes, is determined more by the size of lowercase letters than by
the size of uppercase letters. The `font-size-adjust` property is useful
for adjusting the font size of fallback fonts to keep the aspect value
across fonts consistent, ensuring that the text appears similar
regardless of the font used.

Syntax
------

[css]

```css
/* Keyword */
font-size-adjust: none;

/* One value: <number> or from-font */
font-size-adjust: 0.5;
font-size-adjust: from-font;

/* Two values */
font-size-adjust: ex-height 0.5;
font-size-adjust: ch-width from-font;

/* Global values */
font-size-adjust: inherit;
font-size-adjust: initial;
font-size-adjust: revert;
font-size-adjust: revert-layer;
font-size-adjust: unset;
```

### Values

The `font-size-adjust` property takes as its value the keyword `none`,
one (`<number>` or `from-font`), or two (`<font-metric>` and either
`<number>` or `from-font`) values.

[`none`](#none)

:   No adjustment is applied to the `font-size` value for the fallback
    font.

[`<font-metric>`](#font-metric) [Optional]

:   Specifies the first-choice font metric to use for adjusting the font
    size of the fallback font. This parameter accepts one of the
    keywords listed below. It is an optional parameter, and `ex-height`
    is used if no `<font-metric>` is specified.

    [`ex-height`](#ex-height)

    :   Uses the ratio of x-height (height of lowercase \"x\" in a font)
        to font size (aspect value) to adjust the fallback font size.
        This keyword value is used to normalize lowercase letters across
        fonts.

    [`cap-height`](#cap-height)

    :   Uses the ratio of cap-height (height of uppercase letters) to
        font size to adjust fallback font size. This keyword value is
        used to normalize uppercase letters across fonts.

    [`ch-width`](#ch-width)

    :   Uses the ratio of the advance width (horizontal space taken up
        by a character in a font) of the character \"0\" (ZERO, U+0030)
        to font size. This keyword value is used to normalize horizontal
        narrow pitch of fonts.

    [`ic-width`](#ic-width)

    :   Uses the ratio of the advance width of the character \"水\" (CJK
        water ideograph, U+6C34) to font size. This keyword value is
        used to normalize horizontal wide pitch of fonts, particularly
        those that include CJK (Chinese, Japanese, Korean) characters.

    [`ic-height`](#ic-height)

    :   Uses the ratio of the advance height (vertical space taken up by
        a character in a font) of the character \"水\" (CJK water
        ideograph, U+6C34) to font size. This keyword value is used to
        normalize vertical wide pitch of fonts, particularly those that
        include CJK characters.

[`<number>`](number.md)

:   Adjusts the font size used depending on the specified
    `<font-metric>`. When no `<font-metric>` is specified (in which case
    the default value `ex-height` is used), the `<number>` value adjusts
    the font size of the fallback font so that its x-height is the
    specified multiple of the font size. This value should generally
    match the aspect value (ratio of x-height to font size) of the
    first-choice font. This means that the first-choice font, when
    available, will display consistently across browsers, regardless of
    their support for `font-size-adjust`.

    When a `<font-metric>` value is specified, the `<number>` value
    adjusts the font size as per the chosen `<font-metric>` to maintain
    a consistent appearance for the specified font metric across
    different fonts.

    The `<number>` value accepts any number from `0` to infinity. `0`
    yields text of zero height (that is, the text is hidden). Negative
    values are invalid.

[`from-font`](#from-font)

:   Uses the `<number>` value for the specified `<font-metric>` from the
    first available font.

Description
-----------

To ensure compatibility with browsers that don\'t support
`font-size-adjust`, this property is specified as a numeric multiplier
of the [`font-size`](font-size.md) property. This number should generally
match the aspect value of the first-choice font.

**Note:** If the specified `<font-metric>` has been overridden in
[`@font-face`](@font-face.md), e.g., by using the
[`size-adjust`](size-adjust.md) descriptor, then the overridden
metric will be used in the `font-size-adjust` calculation. This means
that when `font-size-adjust` and `size-adjust` are applied together,
`size-adjust` does not have any effect.

The adjusted font size is calculated using the formula
`u = ( m / m′ ) s`, where:

- `m` is the ratio of the specified `<font-metric>` to the
    first-choice font size.
- `m′` is the ratio of the corresponding `<font-metric>` to the
    fallback font size.
- `s` is the value of the `font-size` property.
- `u` is the new, adjusted font size for the fallback font.

Consider this example to see how the adjusted font size is calculated. A
first-choice font has a `font-size` of `12px` (`s`), and the ratio of
`cap-height` to font size is `0.20` (`m`). The `cap-height` to font size
ratio in the fallback font is `0.15` (`m′`). The `font-size-adjust`
value has been specified as `cap-height 0.20`. If the primary font is
unavailable, the adjusted font size of the fallback font will be
calculated to be `16px` (`(0.20 / 0.15) * 12`). This will ensure that
the `cap-height` of the fallback font is similar to that of the
first-choice font when displayed.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     a [number](number.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-size-adjust = 
  none            |
  <number [0,∞]>  
```

Examples
--------

### Normalizing font size by lowercase and uppercase letters

This example demonstrates how the `font-size-adjust` property can be
used to retain the same aspect value across fonts. The Verdana font has
a relatively high aspect value of `0.545`, which means that the
lowercase letters are relatively tall compared to uppercase letters.
This makes the text in small font sizes appear legible. However, the
Times font has a lower aspect value of `0.447`, so the text is less
legible at small sizes. If Verdana is the first-choice font and Times is
the fallback font, specifying the `font-size-adjust` property can help
to retain the same aspect value in Times. So if the font falls back to
Times, the text will maintain a similar level of legibility as it would
have with Verdana.

Similarly, the cap-height to font size ratio in Verdana is `0.73` and
that in Times is `0.66`. When `font-size-adjust` property is applied to
Times to adjust its uppercase letters to match the ratio in Verdana, the
Times font displays in adjusted font size ((0.73 / 0.66) \* 14)
`15.48px`.

[html]

```html
<p class="verdana">
  A: This text uses the Verdana font (14px), which has relatively large
  lowercase letters.
</p>
<p class="times">
  B: This text uses the Times font (14px), which is hard to read in small sizes.
</p>
<p class="times adjtimesexheight">
  C: This text in 14px Times font is adjusted to the same aspect value as the
  Verdana font, so lowercase letters are normalized across the two fonts.
</p>
<p class="times adjtimescapheight">
  D: This text in 14px Times font is adjusted to the same cap-height to font
  size ratio as the Verdana font, so uppercase letters are normalized across the
  two fonts.
</p>
```

[css]

```css
.times {
  font-family: Times, serif;
  font-size: 14px;
}

.verdana {
  font-family: Verdana, sans-serif;
  font-size: 14px;
}

.adjtimesexheight {
  font-size-adjust: 0.545;
}

.adjtimescapheight {
  font-size-adjust: cap-height 0.73;
}
```

Without `font-size-adjust` in `B`, the switch from Verdana font to Times
font could result in a noticeable decrease in legibility due to its
lower aspect value. In `C`, notice that only one value is specified for
the `font-size-adjust` property, so the default `<font-metric>` value
`ex-height` is used. `D` shows how the font would look compared to `A`
if its uppercase letter height is adjusted.

### Determining the aspect value of a font

For a given font, the same content in two side-by-side
[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)
elements can be used to determine the font\'s aspect value. If the same
font size is used for content in both spans, the spans will match when
the `font-size-adjust` value in one span is accurate for the given font.

In the example below, there are three pairs of side-by-side `<span>`
elements, each containing the letter \"b\". The goal is to adjust the
`font-size-adjust` property for the right `<span>` in each pair until
the borders around the two letters align. The resulting
`font-size-adjust` value can be considered the aspect value for the
font.

Starting at `0.6` in the first pair and adjusting to `0.5` in the
second, we continue adjusting the `font-size-adjust` property value
until the borders around the \"b\" letters align perfectly in the third
pair. In this example, the aspect value is determined to be `0.482`.

[html]

```html
<div>
  <p><span>b</span><span class="adjust1">b</span></p>
  0.6
</div>

<div>
  <p><span>b</span><span class="adjust2">b</span></p>
  0.5
</div>

<div>
  <p><span>b</span><span class="adjust3">b</span></p>
  0.482
</div>
```

[css]

```css
body {
  display: flex;
}

div {
  text-align: center;
}

p {
  font-family: Futura;
  font-size: 50px;
}

span {
  border: solid 1px red;
}

.adjust1 {
  font-size-adjust: 0.6;
}

.adjust2 {
  font-size-adjust: 0.5;
}

.adjust3 {
  font-size-adjust: 0.482;
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 5\
  [\#
  font-size-adjust-prop]](https://drafts.csswg.org/css-fonts-5/#font-size-adjust-prop)

  ----------------------------------------------------------------------------------------------

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

`font-size-adjust`

No

No

3Before Firefox 40, `font-size-adjust: 0` was incorrectly interpreted as
`font-size-adjust: none` ([bug 1144885](https://bugzil.la/1144885)).

1--3Only supported on Windows.

No

No

16.4

No

No

4Before Firefox 40, `font-size-adjust: 0` was incorrectly interpreted as
`font-size-adjust: none` ([bug 1144885](https://bugzil.la/1144885)).

No

16.4

No

`from-font`

No

No

118

No

No

17

No

No

118

No

17

No

`two-values`

No

No

92

No

No

17

No

No

92

No

17

No

See also
--------

- [`font-size`](font-size.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [`size-adjust`](size-adjust.md) `@font-face` descriptor
- [Learn: Fundamental text and font
    styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-size-adjust>

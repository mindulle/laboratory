font-weight
===========

The `font-weight` CSS descriptor allows authors to specify font weights
for the fonts specified in the [`@font-face`](@font-face.md) at-rule.
The [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md) property can separately be used to
set how thick or thin characters in text should be displayed.

For a particular font family, authors can download various font faces
which correspond to the different styles of the same font family, and
then use the `font-weight` descriptor to explicitly specify the font
face\'s weights. The values for the CSS descriptor is same as that of
its corresponding font property.

There are generally limited weights available for a particular font
family. When a specified weight doesn\'t exist, a nearby weight is used.
Fonts lacking bold typeface are often synthesized by the user agent. To
prevent this, use the [`font-synthesis`](font-synthesis.md) shorthand
property.

Syntax
------

[css]

```css
/* Single values */
font-weight: normal;
font-weight: bold;
font-weight: 400;

/* Multiple Values */
font-weight: normal bold;
font-weight: 300 500;
```

The `font-weight` property is described using any one of the values
listed below.

### Values

[`normal`](#normal)

:   Normal font weight. Same as `400`.

[`bold`](#bold)

:   Bold font weight. Same as `700`.

[`<number>`](#number)

:   A [`<number>`](number.md) value between 1 and 1000, inclusive.
    Higher numbers represent weights that are bolder than (or as bold
    as) lower numbers. Certain commonly used values correspond to common
    weight names, as described in the [Common weight name
    mapping](#common_weight_name_mapping) section below.

In earlier versions of the `font-weight` specification, the property
accepts only keyword values and the numeric values 100, 200, 300, 400,
500, 600, 700, 800, and 900; non-variable fonts can only really make use
of these set values, although fine-grained values (e.g. 451) will be
translated to one of these values for non-variable fonts.

CSS Fonts Level 4 extends the syntax to accept any number between 1 and
1000, inclusive, and introduces [Variable fonts](#variable_fonts), which
can make use of this much finer-grained range of font weights.

### Common weight name mapping

The numerical values `100` to `900` roughly correspond to the following
common weight names:

  Value   Common weight name
  ------- ---------------------------
  100     Thin (Hairline)
  200     Extra Light (Ultra Light)
  300     Light
  400     Normal
  500     Medium
  600     Semi Bold (Demi Bold)
  700     Bold
  800     Extra Bold (Ultra Bold)
  900     Black (Heavy)

### Variable fonts

Most fonts have a particular weight which corresponds to one of the
numbers in [Common weight name mapping](#common_weight_name_mapping).
However some fonts, called variable fonts, can support a range of
weights with more or less fine granularity, and this can give the
designer a much closer degree of control over the chosen weight.

For TrueType or OpenType variable fonts, the \"wght\" variation is used
to implement varying weights.

Accessibility concerns
----------------------

People experiencing low vision conditions may have difficulty reading
text set with a `font-weight` value of `100` (Thin/Hairline) or `200`
(Extra Light), especially if the font has a [](_Resources/Markup%20And%20Styling/css/color.md#accessibility_concerns).

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

```text
font-weight = 
  auto                         |
  <font-weight-absolute>  

<font-weight-absolute> = 
  normal             |
  bold               |
  <number [1,1000]>  
```

Examples
--------

### Setting normal font weight in a \@font-face rule

The following finds a local Open Sans font or imports it, and allows
using the font for normal font weights.

[css]

```css
@font-face {
  font-family: "Open Sans";
  src:
    local("Open Sans") format("woff2"),
    url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
  font-weight: 400;
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

See also
--------

- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`src`](src.md)
- [`unicode-range descriptor`](unicode-range.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-weight>

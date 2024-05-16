font-variation-settings
=======================

The `font-variation-settings` CSS property provides low-level control
over [variable font](variable_fonts_guide.md) characteristics by
letting you specify the four letter axis names of the characteristics
you want to vary along with their values.

Try it
------

Syntax
------

[css]

```css
/* Use the default settings */
font-variation-settings: normal;

/* Set values for variable font axis names */
font-variation-settings: "XHGT" 0.7;

/* Global values */
font-variation-settings: inherit;
font-variation-settings: initial;
font-variation-settings: revert;
font-variation-settings: revert-layer;
font-variation-settings: unset;
```

### Values

This property\'s value can take one of two forms:

[`normal`](#normal)

:   Text is laid out using default settings.

[`<string> <number>`](#string_number)

:   When rendering text, the list of variable font axis names is passed
    to the text layout engine to enable or disable font features. Each
    setting is always one or more pairs consisting of a
    [`<string>`](string.md) of 4 ASCII characters followed by a
    [`<number>`](number.md) indicating the axis value to set. If the
    `<string>` has more or fewer characters or contains characters
    outside the U+20 - U+7E code point range, the whole property is
    invalid. The `<number>` can be fractional or negative, depending on
    the value range available in your font, as defined by the font
    designer.

Description
-----------

This property is a low-level mechanism designed to set variable font
features where no other way to enable or access those features exist.
You should only use it when no basic properties exist to set those
features (e.g. [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md),
[`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)).

Font characteristics set using `font-variation-settings` will always
override those set using the corresponding basic font properties, e.g.
`font-weight`, no matter where they appear in the cascade. In some
browsers, this is currently only true when the
[`@font-face`](@font-face.md) declaration includes a
[`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md) range.

### Registered and custom axes

Variable font axes come in two types: **registered** and **custom**.

Registered axes are the most commonly encountered --- common enough that
the authors of the specification felt they were worth standardizing.
Note that this doesn\'t mean that the author has to include all of these
in their font.

Here are the registered axes along with their corresponding CSS
properties:

  Axis Tag           CSS Property
  ------------------ -----------------------------------------------
  \"wght\"           [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
  \"wdth\"           [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md)
  \"slnt\" (slant)   [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md): `oblique + angle`
  \"ital\"           [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md): `italic`
  \"opsz\"           [`font-optical-sizing`](font-optical-sizing.md)

Custom axes can be anything the font designer wants to vary in their
font, for example ascender or descender heights, the size of serifs, or
anything else they can imagine. Any axis can be used as long as it is
given a unique 4-character axis. Some will end up becoming more common,
and may even become registered over time.

**Note:** Registered axis tags are identified using lower-case tags,
whereas custom axes should be given upper-case tags. Note that font
designers aren\'t forced to follow this practice in any way, and some
won\'t. The important takeaway here is that axis tags are
case-sensitive.

To use variable fonts on your operating system, you need to make sure
that it is up to date. For example Linux OSes need the latest Linux
Freetype version, and macOS before 10.13 does not support variable
fonts. If your operating system is not up to date, you will not be able
to use variable fonts in web pages or the Firefox Developer Tools.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     a transform
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-variation-settings = 
  normal                  |
  [ <string> <number> ]#  
```

Examples
--------

You can find a number of other variable font examples in our [](variable_fonts_guide.md).

### Controlling variable font weight (wght)

You can edit the CSS in the example below to play with different font
weight values. See what happens when you specify a value outside the
weight range.

### Controlling variable font slant (slnt)

You can edit the CSS in the example below to play with different font
slant/oblique values.

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variation-settings-def]](https://drafts.csswg.org/css-fonts/#font-variation-settings-def)

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

`font-variation-settings`

62

17

62

No

49

11Requires macOS 10.13 High Sierra or later.

62

62

62

46

11Requires iOS 11 or later.

8.0

See also
--------

- [Variable fonts guide](variable_fonts_guide.md)
- [OpenType font variations
    overview](https://learn.microsoft.com/en-us/typography/opentype/spec/otvaroverview)
    on microsoft.com
- [OpenType design-variation axis tag
    registry](https://docs.microsoft.com/typography/opentype/spec/dvaraxisreg)
    on microsoft.com
- [OpenType variable fonts](https://www.axis-praxis.org/) on
    axis-praxis.org
- [Variable fonts](https://v-fonts.com/) on v-fonts.com

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variation-settings>

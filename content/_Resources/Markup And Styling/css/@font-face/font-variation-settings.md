font-variation-settings
=======================

The `font-variation-settings` CSS descriptor allows authors to specify
low-level OpenType or TrueType font variations in the
[`@font-face`](@font-face.md) at-rule. The values for this descriptor
are the same as the
[`font-variation-settings`](_Resources/Markup%20And%20Styling/css/font-variation-settings.md) property, except
for the global keyword values.

Since this descriptor sets variation values on the font object in the
`@font-face` at-rule and not on an entire element, only some glyphs in
an element may be rendered using this descriptor.

Syntax
------

[css]

```css
/* Use the default settings */
font-variation-settings: normal;

/* Set values for OpenType axis names */
font-variation-settings: "xhgt" 0.7;
```

### Values

[`normal`](#normal)

:   Text is laid out using default settings.

[`<string> <number>`](#string_number)

:   When rendering text, the list of OpenType axis names is passed to
    the text layout engine to enable or disable font features. Each
    setting is always a [`<string>`](string.md) of 4
    [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
    characters, followed by a [`<number>`](number.md) indicating the
    axis value. If the `<string>` has more or fewer characters or
    contains characters outside the U+20 - U+7E code point range, the
    whole property is invalid. The `<number>` can be fractional or
    negative.

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
font-variation-settings = 
  normal                  |
  [ <string> <number> ]#  
```

Examples
--------

### Setting font weight and stretch in a \@font-face rule

[css]

```css
@font-face {
  font-family: "OpenTypeFont";
  src: url("open_type_font.woff2") format("woff2");
  font-weight: normal;
  font-style: normal;
  font-variation-settings:
    "wght" 400,
    "wdth" 300;
}
```

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-rend-desc]](https://drafts.csswg.org/css-fonts/#font-rend-desc)

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

See also
--------

- Other `@font-face` descriptors: [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md),
    [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md),
    [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md),
    [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md), [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md),
    [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md), [`src`](src.md),
    [`unicode-range`](unicode-range.md)
- Related font properties:
    [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md),
    [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/font-variation-settings.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-variation-settings>

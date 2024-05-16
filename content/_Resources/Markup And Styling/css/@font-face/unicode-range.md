unicode-range
=============

The `unicode-range` CSS descriptor sets the specific range of characters
to be used from a font defined using the [`@font-face`](@font-face.md)
at-rule and made available for use on the current page. If the page
doesn\'t use any character in this range, the font is not downloaded; if
it uses at least one, the whole font is downloaded.

Syntax
------

[css]

```css
/* <unicode-range> values */
unicode-range: U+26; /* single code point */
unicode-range: U+0-7F;
unicode-range: U+0025-00FF; /* code point range */
unicode-range: U+4??; /* wildcard range */
unicode-range: U+0025-00FF, U+4??; /* multiple values */
```

### Values

[***single code point***](#single_code_point)

:   A single Unicode character code point, for example `U+26`.

[***code point range***](#code_point_range)

:   A range of Unicode code points. So for example, `U+0025-00FF` means
    *include all characters in the range `U+0025` to `U+00FF`*.

[***wildcard range***](#wildcard_range)

:   A range of Unicode code points containing wildcard characters, that
    is using the `'?'` character, so for example `U+4??` means *include
    all characters in the range `U+400` to `U+4FF`*.

Description
-----------

The purpose of this descriptor is to allow the font resources to be
segmented so that a browser only needs to download the font resource
needed for the text content of a particular page. For example, a site
with many localizations could provide separate font resources for
English, Greek and Japanese. For users viewing the English version of a
page, the font resources for Greek and Japanese fonts wouldn\'t need to
be downloaded, saving bandwidth.

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `U+0-10FFFF`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```
unicode-range = 
  <urange>#  

<urange> = 
  u '+' <ident-token> '?'*            |
  u <dimension-token> '?'*            |
  u <number-token> '?'*               |
  u <number-token> <dimension-token>  |
  u <number-token> <number-token>     |
  u '+' '?'+                          
```

Examples
--------

### Using a different font for a single character

In this example we create a simple HTML containing a single
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
element, including an ampersand, that we want to style with a different
font. To make it obvious, we will use a sans-serif font, *Helvetica*,
for the text, and a serif font, *Times New Roman*, for the ampersand.

In the CSS we are in effect defining a completely separate
[`@font-face`](@font-face.md) that only includes a single character in
it, meaning that only this character will be styled with this font. We
could also have done this by wrapping the ampersand in a
[`<span>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)
and applying a different font just to that, but that is an extra element
and rule set.

#### HTML

[html]

```html
<div>Me & You = Us</div>
```

```css

#### CSS


[css]

```css

@font-face {
  font-family: "Ampersand";
  src: local("Times New Roman");
  unicode-range: U+26;
}

div {
  font-size: 4em;
  font-family: Ampersand, Helvetica, sans-serif;
}

```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  unicode-range-desc]](https://drafts.csswg.org/css-fonts/#unicode-range-desc)

  --------------------------------------------------------------------------------------

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

- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
- [`font-family`](_Resources/Markup%20And%20Styling/css/@font-face/font-family.md)
- [`font-stretch`](_Resources/Markup%20And%20Styling/css/@font-face/font-stretch.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/@font-face/font-style.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/@font-face/font-weight.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)
- [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/@font-face/font-variation-settings.md)
- [`src`](src.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/unicode-range>

font-family
===========

The `font-family` CSS descriptor sets the font family for a font
specified in an [`@font-face`](@font-face.md) at-rule.

The value is used for name matching against a particular `@font-face`
when styling elements using the [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
property. Any name may be used, and this overrides any name specified in
the underlying font data.

Syntax
------

[css]

```css
/* <string> values */
font-family: "font family";
font-family: "another font family";

/* <custom-ident> value */
font-family: examplefont;
```

### Values

[`<family-name>`](#family-name)

:   Specifies the name of the font family.

Formal definition
-----------------

  ------------------------------------- -------------------------------
  Related [at-rule](at-rule.md)         [`@font-face`](@font-face.md)
  [Initial value](initial_value.md)     `n/a (required)`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- -------------------------------

Formal syntax
-------------

```text
font-family = 
  <family-name>  
```

Examples
--------

### Setting the font family name

[css]

```css
@font-face {
  font-family: "Some font family";
  src: url("some_font_name.ttf");
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-family-desc]](https://drafts.csswg.org/css-fonts/#font-family-desc)

  ----------------------------------------------------------------------------------

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

See also
--------

- [`font-display`](_Resources/Markup%20And%20Styling/css/@font-face/font-display.md)
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
https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family>

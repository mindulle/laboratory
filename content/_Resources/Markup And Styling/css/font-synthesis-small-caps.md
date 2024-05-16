font-synthesis-small-caps
=========================

The `font-synthesis-small-caps`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets
you specify whether or not the browser may synthesize small-caps
typeface when it is missing in a font family. Small-caps glyphs
typically use the form of uppercase letters but are reduced to the size
of lowercase letters.

It is often convenient to use the shorthand property
[`font-synthesis`](font-synthesis.md) to control all typeface synthesis
values.

Syntax
------

[css]

```css
/* Keyword values */
font-synthesis-small-caps: auto;
font-synthesis-small-caps: none;

/* Global values */
font-synthesis-small-caps: inherit;
font-synthesis-small-caps: initial;
font-synthesis-small-caps: revert;
font-synthesis-small-caps: revert-layer;
font-synthesis-small-caps: unset;
```

### Values

[`auto`](#auto)

:   Indicates that the missing small-caps typeface may be synthesized by
    the browser if needed.

[`none`](#none)

:   Indicates that the synthesis of the missing small-caps typeface by
    the browser is not allowed.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-synthesis-small-caps = 
  auto  |
  none  
```

Examples
--------

### Disabling synthesis of small-caps typeface

This example shows turning off synthesis of the small-caps typeface by
the browser in the `Montserrat` font.

#### HTML

[html]

```html
<p class="english">
  These are the default <span class="small-caps">small-caps</span>,
  <strong>bold</strong>, and <em>oblique</em> typefaces.
</p>

<p class="english no-syn">
  The <span class="small-caps">small-caps</span> typeface is turned off here but
  not the <strong>bold</strong> and <em>oblique</em> typefaces.
</p>
```

#### CSS

[css]

```css
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

.english {
  font-family: "Montserrat", sans-serif;
}
.small-caps {
  font-variant: small-caps;
}
.no-syn {
  font-synthesis-small-caps: none;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-synthesis-small-caps]](https://drafts.csswg.org/css-fonts/#font-synthesis-small-caps)

  ----------------------------------------------------------------------------------------------------

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

`font-synthesis-small-caps`

97

97

111

No

83

16.4

97

97

111

68

16.4

18.0

See also
--------

- [font-synthesis](font-synthesis.md) shorthand,
    [font-synthesis-style](font-synthesis-style.md),
    [font-synthesis-weight](font-synthesis-weight.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md), [`font-variant`](font-variant.md),
    [`font-variant-caps`](font-variant-caps.md),
    [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [CanvasRenderingContext2D: fontVariantCaps
    property](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fontVariantCaps)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-small-caps>

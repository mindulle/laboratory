font-variant-position
=====================

The `font-variant-position` CSS property controls the use of alternate,
smaller glyphs that are positioned as superscript or subscript.

The glyphs are positioned relative to the baseline of the font, which
remains unchanged. These glyphs are typically used in
[`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub)
and
[`<sup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup)
elements.

When the usage of these alternate glyphs is activated, if one character
in the run doesn\'t have such a typographically-enhanced glyph, the
whole set of characters of the run is rendered using a fallback method,
synthesizing these glyphs.

These alternate glyphs share the same em-box and the same baseline as
the rest of the font. They are merely graphically enhanced, and have no
effect on the line-height and other box characteristics.

Syntax
------

[css]

```css
/* Keyword values */
font-variant-position: normal;
font-variant-position: sub;
font-variant-position: super;

/* Global values */
font-variant-position: inherit;
font-variant-position: initial;
font-variant-position: revert;
font-variant-position: revert-layer;
font-variant-position: unset;
```

The `font-variant-position` property is specified as one of the keyword
values listed below.

### Values

[`normal`](#normal)

:   Deactivates alternate superscript and subscript glyphs.

[`sub`](#sub)

:   Activates subscript alternate glyphs. If, in a given run, one such
    glyph is not available for a character, all the characters in the
    run are rendered using synthesized glyphs.

[`super`](#super)

:   Activates superscript alternate glyphs. If, in a given run, one such
    glyph is not available for a character, all the characters in the
    run are rendered using synthesized glyphs.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-variant-position = 
  normal  |
  sub     |
  super   
```

Examples
--------

### Setting superscript and subscript forms

#### HTML

[html]

```html
<p class="normal">Normal!</p>
<p class="super">Super!</p>
<p class="sub">Sub!</p>
```

#### CSS

[css]

```css
p {
  display: inline;
}

.normal {
  font-variant-position: normal;
}

.super {
  font-variant-position: super;
}

.sub {
  font-variant-position: sub;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variant-position-prop]](https://drafts.csswg.org/css-fonts/#font-variant-position-prop)

  ------------------------------------------------------------------------------------------------------

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

`font-variant-position`

117

117

34

No

103

9.1

117

117

34

No

9.3

No

See also
--------

- [`font-variant`](font-variant.md)
- [`font-variant-alternates`](font-variant-alternates.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-numeric`](font-variant-numeric.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-position>

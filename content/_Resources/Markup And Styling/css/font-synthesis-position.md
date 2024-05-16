font-synthesis-position
=======================

The `font-synthesis-position`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets
you specify whether or not a browser may synthesize the subscript and
superscript \"position\" typefaces when they are missing in a font
family, while using [`font-variant-position`](font-variant-position.md) to
set the positions.

The `font-synthesis-position` property has no effect when using the
[`<sup>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sup)
and
[`<sub>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/sub)
elements.

It is often convenient to use the shorthand property
[`font-synthesis`](font-synthesis.md) to control all typeface synthesis
values.

Syntax
------

[css]

```css
/* Keyword values */
font-synthesis-position: auto;
font-synthesis-position: none;

/* Global values */
font-synthesis-position: inherit;
font-synthesis-position: initial;
font-synthesis-position: revert;
font-synthesis-position: revert-layer;
font-synthesis-position: unset;
```

### Values

[`auto`](#auto)

:   Indicates that a missing position typeface may be synthesized by the
    browser if needed.

[`none`](#none)

:   Indicates that the synthesis of a missing position typeface by the
    browser is not allowed.

Formal definition
-----------------

[Value not found in DB!]

Formal syntax
-------------

Error: could not find syntax for this item

Examples
--------

### Disabling synthesis of position typeface

This example shows turning off synthesis of the superscript and
subscript typefaces by the browser in the `Montserrat` font.

#### HTML

[html]

```html
<p>
  These are the default position <span class="super">superscript</span>,
  position <span class="sub">subscript</span>, <strong>bold</strong> and
  <em>oblique</em> typefaces.
</p>

<p class="no-syn">
  The positions <span class="super">superscript</span> and
  <span class="sub">subscript</span> typeface is turned off here but not the
  <strong>bold</strong> and <em>oblique</em> typefaces (on browsers that support
  <code>font-synthesis-position</code>).
</p>
```

#### CSS

[css]

```css
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

* {
  font-family: "Montserrat", sans-serif;
}
.super {
  font-variant-position: super;
}
.sub {
  font-variant-position: sub;
}
.no-syn {
  font-synthesis-position: none;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-synthesis-position]](https://drafts.csswg.org/css-fonts/#font-synthesis-position)

  ------------------------------------------------------------------------------------------------

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

`font-synthesis-position`

No

No

118

No

No

No

No

No

118

No

No

No

See also
--------

- [`font-synthesis`](font-synthesis.md) shorthand,
    [`font-synthesis-style`](font-synthesis-style.md),
    [`font-synthesis-weight`](font-synthesis-weight.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md), [`font-variant`](font-variant.md),
    [`font-variant-position`](font-variant-position.md),
    [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-position>

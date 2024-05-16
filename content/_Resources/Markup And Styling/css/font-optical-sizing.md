font-optical-sizing
===================

The `font-optical-sizing`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether text rendering is optimized for viewing at different sizes.

Try it
------

Syntax
------

[css]

```css
/* keyword values */
font-optical-sizing: none;
font-optical-sizing: auto; /* default */

/* Global values */
font-optical-sizing: inherit;
font-optical-sizing: initial;
font-optical-sizing: revert;
font-optical-sizing: revert-layer;
font-optical-sizing: unset;
```

### Values

[none](#none)

:   The browser will not modify the shape of glyphs for optimal viewing.

[auto](#auto)

:   The browser will modify the shape of glyphs for optimal viewing.

Description
-----------

Optical sizing is enabled by default for fonts that have an optical size
variation axis. The optical size variation axis is represented by `opsz`
in [`font-variation-settings`](_Resources/Markup%20And%20Styling/css/font-variation-settings.md).

When optical sizing is used, small text sizes are often rendered with
thicker strokes and larger serifs, whereas larger text is often rendered
more delicately with more contrast between thicker and thinner strokes.

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
font-optical-sizing = 
  auto  |
  none  
```

Examples
--------

### Disabling optical sizing

[html]

```html
<p class="optical-sizing">
  This paragraph is optically sized. This is the default across browsers.
</p>

<p class="no-optical-sizing">
  This paragraph is not optically sized. You should see a difference in
  supporting browsers.
</p>
```

[css]

```css
@font-face {
  src: url("AmstelvarAlpha-VF.ttf");
  font-family: "Amstelvar";
  font-style: normal;
}

p {
  font-size: 36px;
  font-family: Amstelvar;
}

.no-optical-sizing {
  font-optical-sizing: none;
}
```

**Note:** The font referenced above --- which includes optical sizing
and is freely-licensed --- is good for testing. You can [download it on
GitHub](https://github.com/googlefonts/amstelvar/releases).

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-optical-sizing-def]](https://drafts.csswg.org/css-fonts/#font-optical-sizing-def)

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

`font-optical-sizing`

79

17

62

No

66

11

79

79

62

57

11

12.0

See also
--------

- [`font-size`](font-size.md)
- [`font-size-adjust`](font-size-adjust.md)
- [Fundamental text and font
    styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-optical-sizing>

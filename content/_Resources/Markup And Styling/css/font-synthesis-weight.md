font-synthesis-weight
=====================

The `font-synthesis-weight`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets
you specify whether or not the browser may synthesize the bold typeface
when it is missing in a font family.

It is often convenient to use the shorthand property
[`font-synthesis`](font-synthesis.md) to control all typeface synthesis
values.

Syntax
------

[css]

```css
/* Keyword values */
font-synthesis-weight: auto;
font-synthesis-weight: none;

/* Global values */
font-synthesis-weight: inherit;
font-synthesis-weight: initial;
font-synthesis-weight: revert;
font-synthesis-weight: revert-layer;
font-synthesis-weight: unset;
```

### Values

[`auto`](#auto)

:   Indicates that the missing bold typeface may be synthesized by the
    browser if needed.

[`none`](#none)

:   Indicates that the synthesis of the missing bold typeface by the
    browser is not allowed.

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
font-synthesis-weight = 
  auto  |
  none  
```

Examples
--------

### Disabling synthesis of bold typeface

This example shows turning off synthesis of the bold typeface by the
browser in the `Montserrat` font.

#### HTML

[html]

```html
<p class="english">
  This is the default <strong>bold typeface</strong> and
  <em>oblique typeface</em>.
</p>

<p class="english no-syn">
  The <strong>bold typeface</strong> is turned off here but not the
  <em>oblique typeface</em>.
</p>
```

#### CSS

[css]

```css
@import url("https://fonts.googleapis.com/css2?family=Montserrat&display=swap");

.english {
  font-family: "Montserrat", sans-serif;
}
.no-syn {
  font-synthesis-weight: none;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-synthesis-weight]](https://drafts.csswg.org/css-fonts/#font-synthesis-weight)

  --------------------------------------------------------------------------------------------

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

`font-synthesis-weight`

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
    [font-synthesis-small-caps](font-synthesis-small-caps.md),
    [font-synthesis-style](font-synthesis-style.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md), [`font-variant`](font-variant.md),
    [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-synthesis-weight>

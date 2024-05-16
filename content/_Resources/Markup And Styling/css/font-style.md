font-style
==========

The `font-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether a font should be styled with a normal, italic, or
oblique face from its [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md).

Try it
------

**Italic** font faces are generally cursive in nature, usually using
less horizontal space than their unstyled counterparts, while
**oblique** faces are usually just sloped versions of the regular face.
When the specified style is not available, both italic and oblique faces
are simulated by artificially sloping the glyphs of the regular face
(use [`font-synthesis`](font-synthesis.md) to control this behavior).

Syntax
------

[css]

```css
font-style: normal;
font-style: italic;
font-style: oblique;
font-style: oblique 10deg;

/* Global values */
font-style: inherit;
font-style: initial;
font-style: revert;
font-style: revert-layer;
font-style: unset;
```

The `font-style` property is specified as a single keyword chosen from
the list of values below, which can optionally include an angle if the
keyword is `oblique`.

### Values

[`normal`](#normal)

:   Selects a font that is classified as `normal` within a
    [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md).

[`italic`](#italic)

:   Selects a font that is classified as `italic`. If no italic version
    of the face is available, one classified as `oblique` is used
    instead. If neither is available, the style is artificially
    simulated.

[`oblique`](#oblique)

:   Selects a font that is classified as `oblique`. If no oblique
    version of the face is available, one classified as `italic` is used
    instead. If neither is available, the style is artificially
    simulated.

[`oblique`](#oblique_2) [`<angle>`](angle.md)

:   Selects a font classified as `oblique`, and additionally specifies
    an angle for the slant of the text. If one or more oblique faces are
    available in the chosen font family, the one that most closely
    matches the specified angle is chosen. If no oblique faces are
    available, the browser will synthesize an oblique version of the
    font by slanting a normal face by the specified amount. Valid values
    are degree values of `-90deg` to `90deg` inclusive. If an angle is
    not specified, an angle of 14 degrees is used. Positive values are
    slanted to the end of the line, while negative values are slanted
    towards the beginning.

    In general, for a requested angle of 14 degrees or greater, larger
    angles are preferred; otherwise, smaller angles are preferred (see
    the spec\'s [font matching
    section](https://drafts.csswg.org/css-fonts-4/#font-matching-algorithm)
    for the precise algorithm).

### Variable fonts

Variable fonts can offer a fine control over the degree to which an
oblique face is slanted. You can select this using the `<angle>`
modifier for the `oblique` keyword.

For TrueType or OpenType variable fonts, the `"slnt"` variation is used
to implement varying slant angles for oblique, and the `"ital"`
variation with a value of 1 is used to implement italic values. See
[`font-variation-settings`](_Resources/Markup%20And%20Styling/css/font-variation-settings.md).

**Note:** For the example below to work, you\'ll need a browser that
supports the CSS Fonts Level 4 syntax in which `font-style: oblique` can
accept an `<angle>`. The demo loads with `font-style: oblique 23deg;`.
Change the value to see the slant of the text change.

Accessibility concerns
----------------------

Large sections of text set with a `font-style` value of `italic` may be
difficult for people with cognitive concerns such as Dyslexia to read.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [W3C Understanding WCAG
    2.1](https://www.w3.org/TR/WCAG21/#visual-presentation)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type; `normal` animates as `oblique 0deg`
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-style = 
  normal                           |
  italic                           |
  oblique <angle [-90deg,90deg]>?  
```

Examples
--------

### Font styles

[css]

```css
.normal {
  font-style: normal;
}

.italic {
  font-style: italic;
}

.oblique {
  font-style: oblique;
}
```

Specifications
--------------

  --------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-style-prop]](https://drafts.csswg.org/css-fonts/#font-style-prop)

  --------------------------------------------------------------------------------

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

`font-style`

1

12

1Before Firefox 44, `oblique` was not distinguished from `italic`.

4

7

1

4.4

18

4Before Firefox 44, `oblique` was not distinguished from `italic`.

10.1

1

1.0

`oblique-angle`

62

79

61

No

49

11.1

62

62

61

46

11.3

8.0

See also
--------

- [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md)
- [Fundamental text and font
    styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-style>

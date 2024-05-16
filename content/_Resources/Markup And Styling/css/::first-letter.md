::first-letter
==============

The `::first-letter`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) applies styles to the first letter of
the first line of a [](visual_formatting_model.md#block-level_elements_and_block_boxes),
but only when not preceded by other content (such as images or inline
tables).

Try it
------

The first letter of an element is not always trivial to identify:

- Punctuation that precedes or immediately follows the first letter is
    included in the match. Punctuation includes any Unicode character
    defined in the *open* (Ps), *close* (Pe), *initial quote* (Pi),
    *final quote* (Pf), and *other punctuation* (Po) classes.
- Some languages have digraphs that are always capitalized together,
    like the `IJ` in Dutch. In these cases, both letters of the digraph
    should be matched by the `::first-letter` pseudo-element.
- A combination of the [`::before`](::before) pseudo-element and the
    [`content`](content.md) property may inject some text at the beginning
    of the element. In that case, `::first-letter` will match the first
    letter of this generated content.

**Note:** CSS introduced the `::first-letter` notation (with two colons)
to distinguish [pseudo-classes](pseudo-classes.md) from
[pseudo-elements](pseudo-elements.md). For backward compatibility, browsers
also accept `:first-letter`, introduced earlier.

Browser support for digraphs such as `IJ` in Dutch is poor. Check the
compatibility table below to see the current state of support.

Allowable properties
--------------------

Only a small subset of CSS properties can be used with the
`::first-letter` pseudo-element:

- All font properties: [`font`](font.md), [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md),
    [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md),
    [`font-kerning`](font-kerning.md),
    [`font-language-override`](font-language-override.md),
    [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md), [`font-synthesis`](font-synthesis.md),
    [`font-variant`](font-variant.md),
    [`font-variant-alternates`](font-variant-alternates.md),
    [`font-variant-caps`](font-variant-caps.md),
    [`font-variant-east-asian`](font-variant-east-asian.md),
    [`font-variant-ligatures`](font-variant-ligatures.md),
    [`font-variant-numeric`](font-variant-numeric.md),
    [`font-variant-position`](font-variant-position.md),
    [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md), [`font-size`](font-size.md),
    [`font-size-adjust`](font-size-adjust.md), [`line-height`](line-height.md)
    and [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- All background properties: [`background`](background.md),
    [`background-color`](background-color.md),
    [`background-image`](background-image.md),
    [`background-clip`](background-clip.md),
    [`background-origin`](background-origin.md),
    [`background-position`](background-position.md),
    [`background-repeat`](background-repeat.md),
    [`background-size`](background-size.md),
    [`background-attachment`](background-attachment.md), and
    [`background-blend-mode`](background-blend-mode.md)
- All margin properties: [`margin`](margin.md),
    [`margin-top`](margin-top.md), [`margin-right`](margin-right.md),
    [`margin-bottom`](margin-bottom.md), [`margin-left`](margin-left.md)
- All padding properties: [`padding`](padding.md),
    [`padding-top`](padding-top.md), [`padding-right`](padding-right.md),
    [`padding-bottom`](padding-bottom.md), [`padding-left`](padding-left.md)
- All border properties: the shorthands [`border`](border.md),
    [`border-style`](border-style.md), [`border-color`](border-color.md),
    [`border-width`](border-width.md), [`border-radius`](border-radius.md),
    [`border-image`](border-image.md), and the longhands properties
- The [`color`](_Resources/Markup%20And%20Styling/css/color.md) property
- The [`text-decoration`](text-decoration.md),
    [`text-shadow`](text-shadow.md), [`text-transform`](text-transform.md),
    [`letter-spacing`](letter-spacing.md), [`word-spacing`](word-spacing.md)
    (when appropriate), [`line-height`](line-height.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-decoration-line`](text-decoration-line.md),
    [`text-decoration-style`](text-decoration-style.md),
    [`box-shadow`](box-shadow.md), [`float`](float.md),
    [`vertical-align`](vertical-align.md) (only if `float` is `none`) CSS
    properties

Syntax
------

[css]

```css
::first-letter {
  /* ... */
}
```

Examples
--------

### Simple drop cap

In this example we will use the `::first-letter` pseudo-element to
create a simple drop cap effect on the first letter of the paragraph
coming right after the `<h2>`.

#### HTML

[html]

```html
<h2>My heading</h2>
<p>
  Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy
  eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam
  voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita
  kasd gubergren, no sea takimata sanctus est.
</p>
<p>
  Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie
  consequat.
</p>
```

#### CSS

[css]

```css
p {
  width: 500px;
  line-height: 1.5;
}

h2 + p::first-letter {
  color: white;
  background-color: black;
  border-radius: 2px;
  box-shadow: 3px 3px 0 red;
  font-size: 250%;
  padding: 6px 3px;
  margin-right: 6px;
  float: left;
}
```

#### Result

### Effect on special punctuation and non-Latin characters

This example illustrates the effect of `::first-letter` on special
punctuation and non-Latin characters.

#### HTML

[html]

```html
<p>
  Duis autem vel eum iriure dolor in hendrerit in vulputate velit esse molestie
  consequat.
</p>
<p>-The beginning of a special punctuation mark.</p>
<p>_The beginning of a special punctuation mark.</p>
<p>"The beginning of a special punctuation mark.</p>
<p>'The beginning of a special punctuation mark.</p>
<p>*The beginning of a special punctuation mark.</p>
<p>#The beginning of a special punctuation mark.</p>
<p>「特殊的汉字标点符号开头。</p>
<p>《特殊的汉字标点符号开头。</p>
<p>"特殊的汉字标点符号开头。</p>
```

#### CSS

[css]

```css
p::first-letter {
  color: red;
  font-size: 150%;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  first-letter-pseudo]](https://drafts.csswg.org/css-pseudo/#first-letter-pseudo)

  -----------------------------------------------------------------------------------------

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

`::first-letter`

11

1212

11

95.5

73.5

11

3737

1818

44

10.110.1

11

1.01.0

`dutch_ij_digraph`

No

No

87

No

No

No

No

No

87

No

No

No

See also
--------

- [`::first-line`](::first-line)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::first-letter>

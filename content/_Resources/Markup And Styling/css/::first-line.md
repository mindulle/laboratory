::first-line
============

The `::first-line`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[pseudo-element](pseudo-elements.md) applies styles to the first line of a
[](visual_formatting_model.md#block-level_elements_and_block_boxes).

Try it
------

The effects of `::first-line` are limited by the length and content of
the first line of text in the element. The length of the first line
depends on many factors, including the width of the element, the width
of the document, and the font size of the text. `::first-line` has no
effect when the first child of the element, which would be the first
part of the first line, is an inline block-level element, such as an
inline table.

**Note:** [Selectors Level
3](https://drafts.csswg.org/selectors-3/#first-line) introduced the
double-colon notation (`::`) to distinguish
[pseudo-classes](pseudo-classes.md) from
[pseudo-elements](pseudo-elements.md), which are single-colon `:`. Browsers
accept both `::first-line` and `:first-line`, which was introduced in
CSS2.

For the purposes of CSS [`background`](background.md), the `::first-line`
pseudo-element is like an inline-level element meaning that in a
left-justified first line, the background may not extend all the way to
the right margin.

Allowable properties
--------------------

Only a small subset of CSS properties can be used with the
`::first-line` pseudo-element:

- All font-related properties: [`font`](font.md),
    [`font-kerning`](font-kerning.md), [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md),
    [`font-variant`](font-variant.md),
    [`font-variant-numeric`](font-variant-numeric.md),
    [`font-variant-position`](font-variant-position.md),
    [`font-variant-east-asian`](font-variant-east-asian.md),
    [`font-variant-caps`](font-variant-caps.md),
    [`font-variant-alternates`](font-variant-alternates.md),
    [`font-variant-ligatures`](font-variant-ligatures.md),
    [`font-synthesis`](font-synthesis.md),
    [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md),
    [`font-language-override`](font-language-override.md),
    [`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md), [`font-size`](font-size.md),
    [`font-size-adjust`](font-size-adjust.md),
    [`font-stretch`](_Resources/Markup%20And%20Styling/css/font-stretch.md), and [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- All background-related properties:
    [`background-color`](background-color.md),
    [`background-clip`](background-clip.md),
    [`background-image`](background-image.md),
    [`background-origin`](background-origin.md),
    [`background-position`](background-position.md),
    [`background-repeat`](background-repeat.md),
    [`background-size`](background-size.md),
    [`background-attachment`](background-attachment.md), and
    [`background-blend-mode`](background-blend-mode.md)
- The [`color`](_Resources/Markup%20And%20Styling/css/color.md) property
- [`word-spacing`](word-spacing.md), [`letter-spacing`](letter-spacing.md),
    [`text-decoration`](text-decoration.md),
    [`text-transform`](text-transform.md), and [`line-height`](line-height.md)
- [`text-shadow`](text-shadow.md), [`text-decoration`](text-decoration.md),
    [`text-decoration-color`](text-decoration-color.md),
    [`text-decoration-line`](text-decoration-line.md),
    [`text-decoration-style`](text-decoration-style.md), and
    [`vertical-align`](vertical-align.md).

Syntax
------

[css]

```css
::first-line {
  /* ... */
}
```

Examples
--------

### HTML

[html]

```html
<p>
  Styles will only be applied to the first line of this paragraph. After that,
  all text will be styled like normal. See what I mean?
</p>

<span>
  The first line of this text will not receive special styling because it is not
  a block-level element.
</span>
```

### CSS

[css]

```css
::first-line {
  color: blue;
  text-transform: uppercase;

  /* WARNING: DO NOT USE THESE */
  /* Many properties are invalid in ::first-line pseudo-elements */
  margin-left: 20px;
  text-indent: 20px;
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  [\#
  first-line-pseudo]](https://drafts.csswg.org/css-pseudo/#first-line-pseudo)

  -------------------------------------------------------------------------------------

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

`::first-line`

1Before Chrome 62, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

1Before Chrome 62, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

1212

11

95.5

7From Opera 15 to Opera 49 (exclusive), the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` or `:first-line`
pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

3.5From Opera 15 to Opera 49 (exclusive), the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` or `:first-line`
pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

1The
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work for `::first-line` or `:first-line`
pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

1The
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work for `::first-line` or `:first-line`
pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

≤37Before WebView 62, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

≤37Before WebView 62, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

18Before Chrome 62, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

18Before Chrome 62, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

44

10.1From Opera 15 to Opera 49 (exclusive), the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` or `:first-line`
pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

10.1From Opera 15 to Opera 49 (exclusive), the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` or `:first-line`
pseudo-elements. See [Chromium bug 129669](https://crbug.com/129669).

1The
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work for `::first-line` or `:first-line`
pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

1The
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work for `::first-line` or `:first-line`
pseudo-elements. See [WebKit bug 3409](https://webkit.org/b/3409).

1.0Before Samsung Internet 8.0, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

1.0Before Samsung Internet 8.0, the
[`text-transform`](https://developer.mozilla.org/docs/Web/CSS/text-transform)
property does not work on `::first-line` pseudo-elements. See [Chromium
bug 129669](https://crbug.com/129669).

See also
--------

- [`::first-letter`](::first-letter)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/::first-line>

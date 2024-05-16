text-orientation
================

The `text-orientation`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the orientation of the text characters in a line. It only affects text
in vertical mode (when [`writing-mode`](writing-mode.md) is not
`horizontal-tb`). It is useful for controlling the display of languages
that use vertical script, and also for making vertical table headers.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
text-orientation: mixed;
text-orientation: upright;
text-orientation: sideways-right;
text-orientation: sideways;
text-orientation: use-glyph-orientation;

/* Global values */
text-orientation: inherit;
text-orientation: initial;
text-orientation: revert;
text-orientation: revert-layer;
text-orientation: unset;
```

The `text-orientation` property is specified as a single keyword from
the list below.

### Values

[`mixed`](#mixed)

:   Rotates the characters of horizontal scripts 90° clockwise. Lays out
    the characters of vertical scripts naturally. Default value.

[`upright`](#upright)

:   Lays out the characters of horizontal scripts naturally (upright),
    as well as the glyphs for vertical scripts. Note that this keyword
    causes all characters to be considered as left-to-right: the used
    value of [`direction`](direction.md) is forced to be `ltr`.

[`sideways`](#sideways)

:   Causes characters to be laid out as they would be horizontally, but
    with the whole line rotated 90° clockwise.

[`sideways-right`](#sideways-right)

:   An alias to `sideways` that is kept for compatibility purposes.

[`use-glyph-orientation`](#use-glyph-orientation)

:   On SVG elements, this keyword leads to use the value of the
    deprecated SVG properties `glyph-orientation-vertical` and
    `glyph-orientation-horizontal`.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------
  [Initial value](initial_value.md)     `mixed`
  Applies to                         all elements, except table row groups, rows, column groups, and columns
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- -------------------------------------------------------------------------

Formal syntax
-------------

```
text-orientation = 
  mixed     |
  upright   |
  sideways  
```

Examples
--------

### HTML

[html]

```html
<p>Lorem ipsum dolet semper quisquam.</p>
```

### CSS

[css]

```css
p {
  writing-mode: vertical-rl;
  text-orientation: upright;
}
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------

  [CSS Writing Modes Level 4\
  [\#
  text-orientation]](https://drafts.csswg.org/css-writing-modes/#text-orientation)

  ------------------------------------------------------------------------------------------

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

`text-orientation`

4811

7979

41

No

3515

145.1

48≤37

4818

41

3514

145

5.01.0

`sideways`

25

79

44`sideways-right` has become an alias of `sideways`.

No

15

7

4.4

25

44`sideways-right` has become an alias of `sideways`.

14

7

1.5

See also
--------

- The other vertical-script related CSS properties:
    [`writing-mode`](writing-mode.md),
    [`text-combine-upright`](text-combine-upright.md), and
    [`unicode-bidi`](unicode-bidi.md).
- [CSS Logical properties](css_logical_properties_and_values.md)
- [Styling vertical text (Chinese, Japanese, Korean and
    Mongolian)](https://www.w3.org/International/articles/vertical-text/)
- Extensive browsers support test results:
    https://w3c.github.io/i18n-tests/results/horizontal-in-vertical.html#text_orientation>

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-orientation>

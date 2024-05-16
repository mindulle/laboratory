text-rendering
==============

The `text-rendering` CSS property provides information to the rendering
engine about what to optimize for when rendering text.

The browser makes trade-offs among speed, legibility, and geometric
precision.

**Note:** The `text-rendering` property is an SVG property that is not
defined in any CSS standard. However, Gecko and WebKit browsers let you
apply this property to HTML and XML content on Windows, macOS, and
Linux.

One very visible effect is `optimizeLegibility`, which enables ligatures
(ff, fi, fl, etc.) in text smaller than 20px for some fonts (for
example, Microsoft\'s *Calibri*, *Candara*, *Constantia*, and *Corbel*,
or the *DejaVu* font family).

Syntax
------

[css]

```css
/* Keyword values */
text-rendering: auto;
text-rendering: optimizeSpeed;
text-rendering: optimizeLegibility;
text-rendering: geometricPrecision;

/* Global values */
text-rendering: inherit;
text-rendering: initial;
text-rendering: revert;
text-rendering: revert-layer;
text-rendering: unset;
```

### Values

[`auto`](#auto) [Non-standard]

:   The browser makes educated guesses about when to optimize for speed,
    legibility, and geometric precision while drawing text. For
    differences in how this value is interpreted by the browser, see the
    compatibility table.

[`optimizeSpeed`](#optimizespeed)

:   The browser emphasizes rendering speed over legibility and geometric
    precision when drawing text. It disables kerning and ligatures.

[`optimizeLegibility`](#optimizelegibility)

:   The browser emphasizes legibility over rendering speed and geometric
    precision. This enables kerning and optional ligatures.

[`geometricPrecision`](#geometricprecision) [Non-standard]

:   The browser emphasizes geometric precision over rendering speed and
    legibility. Certain aspects of fonts --- such as kerning --- don\'t
    scale linearly. So this value can make text using those fonts look
    good.

    In SVG, when text is scaled up or down, browsers calculate the final
    size of the text (which is determined by the specified font size and
    the applied scale) and request a font of that computed size from the
    platform\'s font system. But if you request a font size of, say, 9
    with a scale of 140%, the resulting font size of 12.6 doesn\'t
    explicitly exist in the font system, so the browser rounds the font
    size to 12 instead. This results in stair-step scaling of text.

    But the `geometricPrecision` property --- when fully supported by
    the rendering engine --- lets you scale your text fluidly. For large
    scale factors, you might see less-than-beautiful text rendering, but
    the size is what you would expect---neither rounded up nor down to
    the nearest font size supported by Windows or Linux.

    
    **Note:** WebKit precisely applies the specified value, but Gecko
    treats the value the same as `optimizeLegibility`.

Formal definition
-----------------

  ---------------------------------- ---------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         text elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------

Formal syntax
-------------

```
text-rendering = 
  auto                |
  optimizeSpeed       |
  optimizeLegibility  |
  geometricPrecision  
```

Examples
--------

### Automatic application of optimizeLegibility

This demonstrates how `optimizeLegibility` is used by browsers
automatically when the `font-size` is smaller than `20px`.

#### HTML

[html]

```html
<p class="small">LYoWAT - ff fi fl ffl</p>
<p class="big">LYoWAT - ff fi fl ffl</p>
```

#### CSS

[css]

```css
.small {
  font:
    19.9px "Constantia",
    "Times New Roman",
    "Georgia",
    "Palatino",
    serif;
}
.big {
  font:
    20px "Constantia",
    "Times New Roman",
    "Georgia",
    "Palatino",
    serif;
}
```

#### Result

### optimizeSpeed vs. optimizeLegibility

This example shows the difference between the appearance of
`optimizeSpeed` and `optimizeLegibility` (in your browser; other
browsers may vary).

#### HTML

[html]

```html
<p class="speed">LYoWAT - ff fi fl ffl</p>
<p class="legibility">LYoWAT - ff fi fl ffl</p>
```

#### CSS

[css]

```css
p {
  font:
    1.5em "Constantia",
    "Times New Roman",
    "Georgia",
    "Palatino",
    serif;
}

.speed {
  text-rendering: optimizeSpeed;
}
.legibility {
  text-rendering: optimizeLegibility;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [Scalable Vector Graphics (SVG) 2\
  [\#
  TextRenderingProperty]](https://svgwg.org/svg2-draft/painting.html#TextRenderingProperty)

  ---------------------------------------------------------------------------------------------------

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

`text-rendering`

4\[\"This property is only supported on Windows and Linux.\", \"Initial
versions had bugs on Windows and Linux that broke [font
substitution](https://crbug.com/114719),
[small-caps](https://crbug.com/51973),
[letter-spacing](https://crbug.com/55458) or caused [text to
overlap](https://crbug.com/149548).\"\]

79\[\"This property is only supported on Windows and Linux.\", \"Initial
versions had bugs on Windows and Linux that broke [font
substitution](https://crbug.com/114719),
[small-caps](https://crbug.com/51973),
[letter-spacing](https://crbug.com/55458) or caused [text to
overlap](https://crbug.com/149548).\"\]

1\[\"This property is only supported on Windows and Linux.\", \"The
`optimizeSpeed` option has no effect on Firefox 4 because the standard
code for text rendering is already fast and there is not a faster code
path at this time. See [bug 595688](https://bugzil.la/595688) for
details.\"\]

No

15

5

3From version 3 to 4.3, there is a serious bug where
`text-rendering: optimizeLegibility` causes custom web fonts to not
render. This was fixed in version 4.4.

18\[\"This property is only supported on Windows and Linux.\", \"Initial
versions had bugs on Windows and Linux that broke [font
substitution](https://crbug.com/114719),
[small-caps](https://crbug.com/51973),
[letter-spacing](https://crbug.com/55458) or caused [text to
overlap](https://crbug.com/149548).\"\]

46

14

4.2

1.0This property is only supported on Windows and Linux. Samsung
Internet is not on Windows or Linux.

`auto`

4Chrome treats `auto` as `optimizeSpeed`.

79Edge treats `auto` as `optimizeSpeed`.

1If the font size is 20 pixels or higher, Firefox treats `auto` as
`optimizeLegibility`. For smaller text, Firefox treats `auto` as
`optimizeSpeed`. The 20-pixel threshold can be changed with the
`browser.display.auto_quality_min_font_size` preference.

No

15Opera treats `auto` as `optimizeSpeed`.

5Safari treats `auto` as `optimizeSpeed`. See [WebKit bug
41363](https://webkit.org/b/41363).

≤37WebView treats `auto` as `optimizeSpeed`.

18Chrome treats `auto` as `optimizeSpeed`.

46If the font size is 20 pixels or higher, Firefox treats `auto` as
`optimizeLegibility`. For smaller text, Firefox treats `auto` as
`optimizeSpeed`. The 20-pixel threshold can be changed with the
`browser.display.auto_quality_min_font_size` preference.

14Opera treats `auto` as `optimizeSpeed`.

4.2Safari treats `auto` as `optimizeSpeed`. See [WebKit bug
41363](https://webkit.org/b/41363).

1.0Samsung Internet treats `auto` as `optimizeSpeed`.

`geometricPrecision`

13Supports true geometric precision without rounding up or down to the
nearest supported font size in the operating system.

79Supports true geometric precision without rounding up or down to the
nearest supported font size in the operating system.

1Firefox treats `geometricPrecision` the same as `optimizeLegibility`.

No

15Supports true geometric precision without rounding up or down to the
nearest supported font size in the operating system.

6

37Supports true geometric precision without rounding up or down to the
nearest supported font size in the operating system.

18Supports true geometric precision without rounding up or down to the
nearest supported font size in the operating system.

46Firefox treats `geometricPrecision` the same as `optimizeLegibility`.

14Supports true geometric precision without rounding up or down to the
nearest supported font size in the operating system.

6

1.0Supports true geometric precision without rounding up or down to the
nearest supported font size in the operating system.

See also
--------

- [Drawing text in a
    `<canvas>`](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_text)
- [CSS Text Decoration](css_text_decoration.md) CSS module
- Related CSS properties
  - [`text-decoration`](text-decoration.md) (and its longhand
        properties, such as
        [`text-decoration-line`](text-decoration-line.md),
        [`text-decoration-style`](text-decoration-style.md), and
        [`text-decoration-thickness`](text-decoration-thickness.md))
  - [`text-emphasis`](text-emphasis.md) (and its longhand properties,
        including [`text-emphasis-color`](text-emphasis-color.md),
        [`text-emphasis-position`](text-emphasis-position.md), and
        [`text-emphasis-style`](text-emphasis-style.md))
  - [`text-shadow`](text-shadow.md)
  - [`text-transform`](text-transform.md)
- The [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
    `text-rendering` attribute
- [SVG and
    CSS](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/SVG_and_CSS)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-rendering>

CSS text decoration
===================

The **CSS text decoration** module defines features relating to text
decoration, such as underlines, text shadows, and emphasis marks.

Reference
---------

### Properties

- [`text-decoration`](text-decoration.md)
- [`text-decoration-color`](text-decoration-color.md)
- [`text-decoration-line`](text-decoration-line.md)
- [`text-decoration-skip-ink`](text-decoration-skip-ink.md)
- [`text-decoration-style`](text-decoration-style.md)
- [`text-decoration-thickness`](text-decoration-thickness.md)
- [`text-emphasis`](text-emphasis.md)
- [`text-emphasis-color`](text-emphasis-color.md)
- [`text-emphasis-position`](text-emphasis-position.md)
- [`text-emphasis-style`](text-emphasis-style.md)
- [`text-shadow`](text-shadow.md)
- [`text-underline-offset`](text-underline-offset.md)
- [`text-underline-position`](text-underline-position.md)

Examples
--------

[css]

```css
.under {
  text-decoration: underline red;
}

.over {
  text-decoration: wavy overline lime;
}

.line {
  text-decoration: line-through;
}

.plain {
  text-decoration: none;
}

.underover {
  text-decoration: dashed underline overline;
}

.thick {
  text-decoration: solid underline purple 4px;
}

.blink {
  text-decoration: blink;
}
```

[html]

```html
<p class="under">This text has a line underneath it.</p>
<p class="over">This text has a line over it.</p>
<p class="line">This text has a line going through it.</p>
<p>
  This <a class="plain" href="#">link will not be underlined</a>, as links
  generally are by default. Be careful when removing the text decoration on
  anchors since users often depend on the underline to denote hyperlinks.
</p>
<p class="underover">This text has lines above <em>and</em> below it.</p>
<p class="thick">
  This text has a really thick purple underline in supporting browsers.
</p>
<p class="blink">
  This text might blink for you, depending on the browser you use.
</p>
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Text Decoration Module Level 3\
  ](https://drafts.csswg.org/css-text-decor/)

  -----------------------------------------------------------------------

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_text_decoration>

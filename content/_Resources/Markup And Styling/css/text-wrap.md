text-wrap
=========

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `text-wrap` CSS property controls how text inside an element is
wrapped. The different values provide:

- Typographic improvements, for example more balanced line lengths
    across broken headings
- A way to turn text wrapping off completely.

**Note:** The [`white-space-collapse`](white-space-collapse.md) and
`text-wrap` properties can be declared together using the
[`white-space`](white-space.md) shorthand property.

Syntax
------

[css]

```css
/* Keyword values */
text-wrap: wrap;
text-wrap: nowrap;
text-wrap: balance;

/* Global values */
text-wrap: inherit;
text-wrap: initial;
text-wrap: revert;
text-wrap: revert-layer;
text-wrap: unset;
```

The `text-wrap` property is specified as a single keyword chosen from
the list of values below.

### Values

[`wrap`](#wrap)

:   Text is wrapped across lines at appropriate characters (for example
    spaces, in languages like English that use space separators) to
    minimize overflow. This is the default value.

[`nowrap`](#nowrap)

:   Text does not wrap across lines. It will overflow its containing
    element rather than breaking onto a new line.

[`balance`](#balance)

:   Text is wrapped in a way that best balances the number of characters
    on each line, enhancing layout quality and legibility. Because
    counting characters and balancing them across multiple lines is
    computationally expensive, this value is only supported for blocks
    of text spanning a limited number of lines (the Chromium
    implementation uses six wrapped lines or less), meaning that it is
    useful for cases such as headings or pull quotes.

Formal definition
-----------------

  ---------------------------------- ---------------------------
  [Initial value](initial_value.md)     `wrap`
  Applies to                         text and block containers
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------

Formal syntax
-------------

```
text-wrap = 
  wrap     |
  nowrap   |
  balance  |
  stable   |
  pretty   
```

Examples
--------

### Basic text wrap value comparison

#### HTML

[html]

```html
<h2 class="wrap" contenteditable="true">
  The default behavior; the text in the heading wraps "normally"
</h2>

<h2 class="nowrap" contenteditable="true">
  In this case the text in the heading doesn't wrap, and overflows the container
</h2>

<h2 class="balance" contenteditable="true">
  In this case the text in the heading is nicely balanced across lines
</h2>
```

### CSS

[css]

```css
.wrap {
  text-wrap: wrap;
}

.nowrap {
  text-wrap: nowrap;
}

.balance {
  text-wrap: balance;
}

h2 {
  font-size: 2rem;
  font-family: sans-serif;
}
```

#### Result

The text in the example is editable. Change the text, adding long words,
to view how the different line and word lengths impact wrapping.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Text Module Level 4\
  [\# text-wrap]](https://drafts.csswg.org/css-text-4/#text-wrap)

  -----------------------------------------------------------------------

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

`text-wrap`

114The `pretty` and `stable` values are not supported.

114The `pretty` and `stable` values are not supported.

No

No

100The `pretty` and `stable` values are not supported.

No

114The `pretty` and `stable` values are not supported.

114The `pretty` and `stable` values are not supported.

No

NoThe `pretty` and `stable` values are not supported.

No

NoThe `pretty` and `stable` values are not supported.

`pretty`

117

117

No

No

103

No

117

117

No

No

No

No

See also
--------

- [`white-space`](white-space.md)
- [`white-space-collapse`](white-space-collapse.md)
- [CSS text module](css_text.md)
- [CSS
    `text-wrap: balance`](https://developer.chrome.com/blog/css-text-wrap-balance/)
    on developer.chrome.com

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-wrap>

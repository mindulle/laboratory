text-underline-offset
=====================

The `text-underline-offset`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the offset distance of an underline text decoration line (applied using
[`text-decoration`](text-decoration.md)) from its original position.

Try it
------

`text-underline-offset` is not part of the
[`text-decoration`](text-decoration.md) shorthand. While an element can
have multiple `text-decoration` lines, `text-underline-offset` only
impacts underlining, and **not** other possible line decoration options
such as `overline` or `line-through`.

Syntax
------

[css]

```css
/* Single keyword */
text-underline-offset: auto;

/* length */
text-underline-offset: 0.1em;
text-underline-offset: 3px;

/* percentage */
text-underline-offset: 20%;

/* Global values */
text-underline-offset: inherit;
text-underline-offset: initial;
text-underline-offset: revert;
text-underline-offset: revert-layer;
text-underline-offset: unset;
```

The `text-underline-offset` property is specified as a single value from
the list below.

### Values

[`auto`](#auto)

:   The browser chooses the appropriate offset for underlines.

[`<length>`](#length)

:   Specifies the offset of underlines as a [`<length>`](length.md),
    overriding the font file suggestion and the browser default. It is
    recommended to use `em` units so the offset scales with the font
    size.

[`<percentage>`](#percentage)

:   Specifies the offset of underlines as a [`<percentage>`](percentage.md)
    of **1 em** in the element\'s font. A percentage inherits as a
    relative value, and so therefore scales with changes in the font.
    For a given application of this property, the offset is constant
    across the whole box that the underline is applied to, even if there
    are child elements with different font sizes or vertical alignment.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  Percentages                        refer to the font size of the element itself
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-underline-offset = 
  auto          |
  <length>      |
  <percentage>  
```

Examples
--------

### Demonstration of text-underline-offset

[html]

```html
<p class="oneline">Here's some text with an offset wavy red underline!</p>
<br />
<p class="twolines">
  This text has lines both above and below it. Only the bottom one is offset.
</p>
```

[css]

```css
p {
  text-decoration: underline wavy red;
  text-underline-offset: 1em;
}

.twolines {
  text-decoration-color: purple;
  text-decoration-line: underline overline;
}
```

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 4\
  [\#
  underline-offset]](https://drafts.csswg.org/css-text-decor-4/#underline-offset)

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

`text-underline-offset`

87

87

70

No

73

12.1

87

87

79

62

12.2

14.0

`percentage`

87

87

74

No

73

No

87

87

79

62

No

14.0

See also
--------

- [`text-decoration`](text-decoration.md)
- [`text-decoration-thickness`](text-decoration-thickness.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-underline-offset>

text-decoration-thickness
=========================

The `text-decoration-thickness`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the stroke thickness of the decoration line that is used on text in an
element, such as a line-through, underline, or overline.

Try it
------

Syntax
------

[css]

```css
/* Single keyword */
text-decoration-thickness: auto;
text-decoration-thickness: from-font;

/* length */
text-decoration-thickness: 0.1em;
text-decoration-thickness: 3px;

/* percentage */
text-decoration-thickness: 10%;

/* Global values */
text-decoration-thickness: inherit;
text-decoration-thickness: initial;
text-decoration-thickness: revert;
text-decoration-thickness: revert-layer;
text-decoration-thickness: unset;
```

### Values

[`auto`](#auto)

:   The browser chooses an appropriate width for the text decoration
    line.

[`from-font`](#from-font)

:   If the font file includes information about a preferred thickness,
    use that value. If the font file doesn\'t include this information,
    behave as if `auto` was set, with the browser choosing an
    appropriate thickness.

[`<length>`](#length)

:   Specifies the thickness of the text decoration line as a
    [`<length>`](length.md), overriding the font file suggestion or the
    browser default.

[`<percentage>`](#percentage)

:   Specifies the thickness of the text decoration line as a
    [`<percentage>`](percentage.md) of **1em** in the current font. A
    percentage inherits as a relative value, and so therefore scales
    with changes in the font. The browser must use a minimum of 1 device
    pixel. For a given application of this property, the thickness is
    constant across the whole box it is applied to, even if there are
    child elements with a different font size.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           no
  Percentages                        refer to the font size of the element itself
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-decoration-thickness = 
  auto          |
  from-font     |
  <length>      |
  <percentage>  
```

Examples
--------

### Varying thickness

#### HTML

[html]

```html
<p class="thin">Here's some text with a 1px red underline.</p>
<p class="thick">This one has a 5px red underline.</p>
<p class="shorthand">This uses the equivalent shorthand.</p>
```

#### CSS

[css]

```css
.thin {
  text-decoration-line: underline;
  text-decoration-style: solid;
  text-decoration-color: red;
  text-decoration-thickness: 1px;
}

.thick {
  text-decoration-line: underline;
  text-decoration-style: solid;
  text-decoration-color: red;
  text-decoration-thickness: 5px;
}

.shorthand {
  text-decoration: underline solid red 5px;
}
```

#### Results

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------------------

  [CSS Text Decoration Module Level 4\
  [\#
  text-decoration-width-property]](https://drafts.csswg.org/css-text-decor-4/#text-decoration-width-property)

  ---------------------------------------------------------------------------------------------------------------------

**Note:** The property used to be called `text-decoration-width`, but
was updated in 2019 to `text-decoration-thickness`.

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

`text-decoration-thickness`

89

87--89The `text-decoration-thickness` property does not work unless
either `text-underline-offset` is set to something other than `auto` or
`text-decoration-color` is set to something other than `currentColor`.
See [Chromium bug 1154537](https://crbug.com/1154537).

89

87--89The `text-decoration-thickness` property does not work unless
either `text-underline-offset` is set to something other than `auto` or
`text-decoration-color` is set to something other than `currentColor`.
See [Chromium bug 1154537](https://crbug.com/1154537).

70

No

75

73--75The `text-decoration-thickness` property does not work unless
either `text-underline-offset` is set to something other than `auto` or
`text-decoration-color` is set to something other than `currentColor`.
See [Chromium bug 1154537](https://crbug.com/1154537).

12.1

89

87--89The `text-decoration-thickness` property does not work unless
either `text-underline-offset` is set to something other than `auto` or
`text-decoration-color` is set to something other than `currentColor`.
See [Chromium bug 1154537](https://crbug.com/1154537).

89

87--89The `text-decoration-thickness` property does not work unless
either `text-underline-offset` is set to something other than `auto` or
`text-decoration-color` is set to something other than `currentColor`.
See [Chromium bug 1154537](https://crbug.com/1154537).

79

63

62--63The `text-decoration-thickness` property does not work unless
either `text-underline-offset` is set to something other than `auto` or
`text-decoration-color` is set to something other than `currentColor`.
See [Chromium bug 1154537](https://crbug.com/1154537).

12.2

15.0

14.0--15.0The `text-decoration-thickness` property does not work unless
either `text-underline-offset` is set to something other than `auto` or
`text-decoration-color` is set to something other than `currentColor`.
See [Chromium bug 1154537](https://crbug.com/1154537).

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
- [`text-underline-offset`](text-underline-offset.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness>

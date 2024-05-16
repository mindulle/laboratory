initial-letter-align
====================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `initial-letter-align` CSS property specifies the alignment of
initial letters within a paragraph.

Syntax
------

[css]

```css
/* Keyword values */
initial-letter-align: auto;
initial-letter-align: alphabetic;
initial-letter-align: hanging;
initial-letter-align: ideographic;

/* Global values */
initial-letter-align: inherit;
initial-letter-align: initial;
initial-letter-align: revert;
initial-letter-align: revert-layer;
initial-letter-align: unset;
```

One of the keyword values listed below.

### Values

[`auto`](#auto)

:   The user agent selects the value which corresponds to the language
    of the text. Western languages would default to alphabetic, CJK
    languages to ideographic, and some Indic languages to hanging.

[`alphabetic`](#alphabetic)

:   As described above, the cap height of the initial letter aligns with
    the cap height of the first line of text. The baseline of the
    initial letter aligns with the baseline of the Nth text baseline.

[`hanging`](#hanging)

:   The hanging baseline of the initial letter aligns with the hanging
    baseline of the first line of text.

[`ideographic`](#ideographic)

:   The initial letter is centered in the N-line area.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         [`::first-letter`](::first-letter) pseudo-elements and inline-level first child of a block container
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
initial-letter-align = 
  [ border-box? [ alphabetic | ideographic | hanging | leading ]? ]!  
```

Examples
--------

### Aligning initial letter

#### HTML

[html]

```html
<p class="auto ">Initial letter - auto</p>
<p class="alphabetic">Initial letter - alphabetic</p>
<p class="hanging">Initial letter - hanging</p>
<p class="ideographic">Initial letter - ideographic</p>
```

#### CSS

[css]

```css
.auto::first-letter {
  -webkit-initial-letter-align: auto;
  initial-letter-align: auto;
}

.alphabetic::first-letter {
  -webkit-initial-letter-align: alphabetic;
  initial-letter-align: alphabetic;
}

.hanging::first-letter {
  -webkit-initial-letter-align: hanging;
  initial-letter-align: hanging;
}

.ideographic::first-letter {
  -webkit-initial-letter-align: ideographic;
  initial-letter-align: ideographic;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [CSS Inline Layout Module Level 3\
  [\#
  aligning-initial-letter]](https://drafts.csswg.org/css-inline/#aligning-initial-letter)

  -------------------------------------------------------------------------------------------------

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

`initial-letter-align`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

- [`initial-letter`](initial-letter.md)
- [Drop caps in
    CSS](https://www.oddbird.net/2017/01/03/initial-letter/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/initial-letter-align>

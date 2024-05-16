line-break
==========

The `line-break` CSS property sets how to break lines of Chinese,
Japanese, or Korean (CJK) text when working with punctuation and
symbols.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
line-break: auto;
line-break: loose;
line-break: normal;
line-break: strict;
line-break: anywhere;

/* Global values */
line-break: inherit;
line-break: initial;
line-break: revert;
line-break: revert-layer;
line-break: unset;
```

### Values

[`auto`](#auto)

:   Break text using the default line break rule.

[`loose`](#loose)

:   Break text using the least restrictive line break rule. Typically
    used for short lines, such as in newspapers.

[`normal`](#normal)

:   Break text using the most common line break rule.

[`strict`](#strict)

:   Break text using the most stringent line break rule.

[`anywhere`](#anywhere)

:   There is a soft wrap opportunity around every typographic character
    unit, including around any punctuation character or preserved white
    spaces, or in the middle of words, disregarding any prohibition
    against line breaks, even those introduced by characters with the
    GL, WJ, or ZWJ character class or mandated by the
    [`word-break`](word-break.md) property. The different wrapping
    opportunities must not be prioritized. Hyphenation is not applied.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
line-break = 
  auto      |
  loose     |
  normal    |
  strict    |
  anywhere  
```

Examples
--------

### Setting text wrapping

See whether the text is wrapped before \"々\", \"ぁ\" and \"。\".

#### HTML

[html]

```html
<div lang="ja">
  <p class="wrapbox auto">
    auto:<br />そこは湖のほとりで木々が輝いていた。<br />その景色に、美しいなぁと思わずつぶやいた。
  </p>
  <p class="wrapbox loose">
    loose:<br />そこは湖のほとりで木々が輝いていた。<br />その景色に、美しいなぁと思わずつぶやいた。
  </p>
  <p class="wrapbox normal">
    normal:<br />そこは湖のほとりで木々が輝いていた。<br />その景色に、美しいなぁと思わずつぶやいた。
  </p>
  <p class="wrapbox strict">
    strict:<br />そこは湖のほとりで木々が輝いていた。<br />その景色に、美しいなぁと思わずつぶやいた。
  </p>
  <p class="wrapbox anywhere">
    anywhere:<br />そこは湖のほとりで木々が輝いていた。<br />その景色に、美しいなぁと思わずつぶやいた。
  </p>
</div>
```

#### CSS

[css]

```css
.wrapbox {
  width: 10em;
  margin: 0.5em;
  white-space: normal;
  vertical-align: top;
  display: inline-block;
}
.auto {
  line-break: auto;
}
.loose {
  line-break: loose;
}
.normal {
  line-break: normal;
}
.strict {
  line-break: strict;
}
.anywhere {
  line-break: anywhere;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  line-break-property]](https://drafts.csswg.org/css-text/#line-break-property)

  ---------------------------------------------------------------------------------------

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

`line-break`

581

14

69

85.5

4515

1132--3

58≤37

5818

79

4314

111

7.01.0

- [CSS and International
    text](https://www.w3.org/International/articles/css3-text/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/line-break>

ruby-position
=============

The `ruby-position` CSS property defines the position of a ruby element
relatives to its base element. It can be positioned over the element
(`over`), under it (`under`), or between the characters on their right
side (`inter-character`).

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
ruby-position: over;
ruby-position: under;
ruby-position: inter-character;
ruby-position: alternate;

/* Global values */
ruby-position: inherit;
ruby-position: initial;
ruby-position: revert;
ruby-position: revert-layer;
ruby-position: unset;
```

### Values

[`over`](#over)

:   Is a keyword indicating that the ruby has to be placed
    over the main text for horizontal scripts and right to it for
    vertical scripts.

[`under`](#under)

:   Is a keyword indicating that the ruby has to be placed
    under the main text for horizontal scripts and left to it for
    vertical scripts.

[`inter-character`](#inter-character) [Experimental]

:   Is a keyword indicating that the ruby has to be placed between the
    different characters.

[`alternate`](#alternate) [Experimental]

:   Is a keyword indicating that the ruby alternates between over and
    under, when there are multiple levels of annotation.

Formal definition
-----------------

  ---------------------------------- -----------------------------
  [Initial value](initial_value.md)     `alternate`
  Applies to                         ruby annotations containers
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------------------

Formal syntax
-------------

```
ruby-position = 
  [ alternate || [ over | under ] ]  |
  inter-character                    
```

Examples
--------

### Ruby positioned over the text

#### HTML

[html]

```html
<ruby>
  <rb>超電磁砲</rb>
  <rp>（</rp><rt>レールガン</rt><rp>）</rp>
</ruby>
```

#### CSS

[css]

```css
ruby {
  ruby-position: over;
}
```

#### Result

### Ruby positioned under the text

#### HTML

[html]

```html
<ruby>
  <rb>超電磁砲</rb>
  <rp>（</rp><rt>レールガン</rt><rp>）</rp>
</ruby>
```

#### CSS

[css]

```css
ruby {
  ruby-position: under;
}
```

#### Result

### Ruby alternate

#### HTML

[html]

```html
<ruby>
  <rb>A</rb><rb>B</rb><rb>C</rb>
  <rtc>Above</rtc>
  <rtc>Below</rtc>
</ruby>
```

#### CSS

[css]

```css
ruby {
  ruby-position: alternate; /* this is also the initial value */
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Ruby Annotation Layout Module Level 1\
  [\# rubypos]](https://drafts.csswg.org/css-ruby/#rubypos)

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

`ruby-position`

84

1Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

84

79Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

12--79

38

NoInternet Explorer 9 and later support an old draft values: `inline`
(equivalent of having `display: inline` on the ruby), and `above`
(synonym of the modern `over`).

70

15Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

7Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

84

4.4Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

84

18Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

38

60

14Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

7Implemented as a non-standard, prefixed, version of `ruby-position`,
`-webkit-ruby-position`: it has two properties: `before` and `after`
(both equivalent, for ltr and rtl scripts to the standard `over` value
used with `ruby-align: start`).

14.0

`alternate`

No

No

88

No

No

No

No

No

88

No

No

No

`inter-character`

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

- HTML Ruby elements:
    [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby),
    [`<rt>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rt),
    [`<rp>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rp),
    and
    [`<rtc>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/rtc).
- CSS Ruby properties: [`ruby-align`](ruby-align.md),
    [`ruby-merge`].

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/ruby-position>

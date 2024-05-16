text-transform
==============

The `text-transform` CSS property specifies how to capitalize an
element\'s text. It can be used to make text appear in all-uppercase or
all-lowercase, or with each word capitalized. It also can help improve
legibility for ruby.

Try it
------

The `text-transform` property takes into account language-specific case
mapping rules such as the following:

- In Turkic languages, like Turkish (`tr`), Azerbaijani (`az`),
    Crimean Tatar (`crh`), Volga Tatar (`tt`), and Bashkir (`ba`), there
    are two kinds of `i`, with and without the dot, and two case
    pairings: `i`/`İ` and `ı`/`I`.
- In German (`de`), the `ß` becomes `SS` in uppercase.
- In Dutch (`nl`), the `ij` digraph becomes `IJ`, even with
    `text-transform: capitalize`, which only puts the first letter of a
    word in uppercase.
- In Greek (`el`), vowels lose their accent when the whole word is in
    uppercase (`ά`/`Α`), except for the disjunctive eta (`ή`/`Ή`). Also,
    diphthongs with an accent on the first vowel lose the accent and
    gain a diaeresis on the second vowel (`άι`/`ΑΪ`).
- In Greek (`el`), the lowercase sigma character has two forms: `σ`
    and `ς`. `ς` is used only when sigma terminates a word. When
    applying `text-transform: lowercase` to an uppercase sigma (`Σ`),
    the browser needs to choose the right lowercase form based on
    context.
- in Irish (`ga`), certain prefixed letters remain in lowercase when
    the base initial is capitalized, so for example
    `text-transform: uppercase` will change `ar aon tslí` to
    `AR AON tSLÍ` and not, as one might expect, `AR AON TSLÍ` (Firefox
    only). In some cases, a hyphen is also removed upon uppercasing:
    `an t-uisce` transforms to `AN tUISCE` (and the hyphen is correctly
    reinserted by `text-transform: lowercase`).

The language is defined by the
[`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/lang)
HTML attribute or the
[`xml:lang`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/xml:lang)
XML attribute.

**Note:** Support for language-specific cases varies between browsers,
so check the [browser compatibility table](#browser_compatibility).

Syntax
------

[css]

```css
/* Keyword values */
text-transform: none;
text-transform: capitalize;
text-transform: uppercase;
text-transform: lowercase;
text-transform: full-width;
text-transform: full-size-kana;

/* Global values */
text-transform: inherit;
text-transform: initial;
text-transform: revert;
text-transform: revert-layer;
text-transform: unset;
```

[`capitalize`](#capitalize)

:   Is a keyword that converts the first *letter* of each word to
    uppercase. Other characters remain unchanged (they retain their
    original case as written in the element\'s text). A letter is
    defined as a character that is part of Unicode\'s Letter or Number
    general categories [Experimental] ; thus, any
    punctuation marks or symbols at the beginning of a word are ignored.

    **Note:** Authors should not expect `capitalize` to follow
    language-specific title casing conventions (such as skipping
    articles in English).
    

    
    **Note:** The `capitalize` keyword was under-specified in CSS 1 and
    CSS 2.1. This resulted in differences between browsers in the way
    the first letter was calculated (Firefox considered `-` and `_` as
    letters, but other browsers did not. Both Webkit and Gecko
    incorrectly considered letter-based symbols like `ⓐ` to be real
    letters.) By precisely defining the correct behavior, CSS Text Level
    3 cleans this mess up. The `capitalize` line in the browser
    compatibility table contains the version the different engines
    started to support this now precisely-defined behavior.

[`uppercase`](#uppercase)

:   Is a keyword that converts all characters to uppercase.

[`lowercase`](#lowercase)

:   Is a keyword that converts all characters to lowercase.

[`none`](#none)

:   Is a keyword that prevents the case of all characters from being
    changed.

[`full-width`](#full-width)

:   Is a keyword that forces the writing of a character --- mainly
    ideograms and Latin scripts --- inside a square, allowing them to be
    aligned in the usual East Asian scripts (like Chinese or Japanese).

[`full-size-kana`](#full-size-kana)

:   Generally used for
    [`<ruby>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ruby)
    annotation text, the keyword converts all small Kana characters to
    the equivalent full-size Kana, to compensate for legibility issues
    at the small font sizes typically used in ruby.

Accessibility concerns
----------------------

Large sections of text set with a `text-transform` value of `uppercase`
may be difficult for people with cognitive concerns such as Dyslexia to
read.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [W3C Understanding WCAG
    2.1](https://www.w3.org/TR/WCAG21/#visual-presentation)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-transform = 
  none                                                |
  [ capitalize | uppercase | lowercase ] || full-width || full-size-kana  |
  math-auto                                           |
  math-bold                                           |
  math-italic                                         |
  math-bold-italic                                    |
  math-double-struck                                  |
  math-bold-fraktur                                   |
  math-script                                         |
  math-bold-script                                    |
  math-fraktur                                        |
  math-sans-serif                                     |
  math-bold-sans-serif                                |
  math-sans-serif-italic                              |
  math-sans-serif-bold-italic                         |
  math-monospace                                      |
  math-initial                                        |
  math-tailed                                         |
  math-looped                                         |
  math-stretched                                      
```

Examples
--------

### Example using \"none\"

[html]

```html
<p>
  Initial String
  <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit…</strong>
</p>
<p>
  text-transform: none
  <strong
    ><span
      >Lorem ipsum dolor sit amet, consectetur adipisicing elit…</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: none;
}
strong {
  float: right;
}
```

This demonstrates no text transformation.

### Example using \"capitalize\" (general)

[html]

```html
<p>
  Initial String
  <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit…</strong>
</p>
<p>
  text-transform: capitalize
  <strong
    ><span
      >Lorem ipsum dolor sit amet, consectetur adipisicing elit…</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: capitalize;
}
strong {
  float: right;
}
```

This demonstrates text capitalization.

### Example using \"capitalize\" (punctuation)

[html]

```html
<p>
  Initial String
  <strong
    >(this) "is" [a] –short– -test- «for» *the* _css_ ¿capitalize?
    ?¡transform!</strong
  >
</p>
<p>
  text-transform: capitalize
  <strong
    ><span
      >(this) "is" [a] –short– -test- «for» *the* _css_ ¿capitalize?
      ?¡transform!</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: capitalize;
}
strong {
  float: right;
}
```

This demonstrates how initial punctuations of a word are ignored. The
keyword target the first letter, that is the first Unicode character
part of the Letter or Number general category.

### Example using \"capitalize\" (Symbols)

[html]

```html
<p>
  Initial String
  <strong>ⓐⓑⓒ (ⓓⓔⓕ) —ⓖⓗⓘ— ⓙkl</strong>
</p>
<p>
  text-transform: capitalize
  <strong><span>ⓐⓑⓒ (ⓓⓔⓕ) —ⓖⓗⓘ— ⓙkl</span></strong>
</p>
```

[css]

```css
span {
  text-transform: capitalize;
}
strong {
  float: right;
}
```

This demonstrates how initial symbols are ignored. The keyword target
the first letter, that is the first Unicode character part of the Letter
or Number general category.

### Example using \"capitalize\" (Dutch ij digraph)

[html]

```html
<p>
  Initial String
  <strong lang="nl">The Dutch word: "ijsland" starts with a digraph.</strong>
</p>
<p>
  text-transform: capitalize
  <strong
    ><span lang="nl"
      >The Dutch word: "ijsland" starts with a digraph.</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: capitalize;
}
strong {
  float: right;
}
```

This demonstrates how the Dutch *ij* digraph must be handled like one
single letter.

### Example using \"uppercase\" (general)

[html]

```html
<p>
  Initial String
  <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit…</strong>
</p>
<p>
  text-transform: uppercase
  <strong
    ><span
      >Lorem ipsum dolor sit amet, consectetur adipisicing elit…</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: uppercase;
}
strong {
  float: right;
}
```

This demonstrates transforming the text to uppercase.

### Example using \"uppercase\" (Greek vowels)

[html]

```html
<p>
  Initial String
  <strong>Θα πάμε στο "Θεϊκό φαΐ" ή στη "Νεράιδα"</strong>
</p>
<p>
  text-transform: uppercase
  <strong
    ><span lang="el">Θα πάμε στο "Θεϊκό φαΐ" ή στη "Νεράιδα"</span></strong
  >
</p>
```

[css]

```css
span {
  text-transform: uppercase;
}
strong {
  float: right;
}
```

This demonstrates how Greek vowels except disjunctive *eta* should have
no accent, and the accent on the first vowel of a vowel pair becomes a
diaeresis on the second vowel.

### Example using \"lowercase\" (general)

[html]

```html
<p>
  Initial String
  <strong>Lorem ipsum dolor sit amet, consectetur adipisicing elit…</strong>
</p>
<p>
  text-transform: lowercase
  <strong
    ><span
      >Lorem ipsum dolor sit amet, consectetur adipisicing elit…</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: lowercase;
}
strong {
  float: right;
}
```

This demonstrates transforming the text to lowercase.

### Example using \"lowercase\" (Greek Σ)

[html]

```html
<p>
  Initial String
  <strong>Σ IS A greek LETTER that appears SEVERAL TIMES IN ΟΔΥΣΣΕΥΣ.</strong>
</p>
<p>
  text-transform: lowercase
  <strong
    ><span
      >Σ IS A greek LETTER that appears SEVERAL TIMES IN ΟΔΥΣΣΕΥΣ.</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: lowercase;
}
strong {
  float: right;
}
```

This demonstrates how the Greek character sigma (`Σ`) is transformed
into the regular lowercase sigma (`σ`) or the word-final variant (`ς`),
according the context.

### Example using \"lowercase\" (Lithuanian)

[html]

```html
<p>
  Initial String
  <strong>Ĩ is a Lithuanian LETTER as is J́</strong>
</p>
<p>
  text-transform: lowercase
  <strong><span lang="lt">Ĩ is a Lithuanian LETTER as is J́</span></strong>
</p>
```

[css]

```css
span {
  text-transform: lowercase;
}
strong {
  float: right;
}
```

This demonstrates how the Lithuanian letters `Ĩ` and `J́` retain their
dot when transformed to lowercase.

### Example using \"full-width\" (general)

[html]

```html
<p>
  Initial String
  <strong
    >0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&()*+,-./:;<=>?@~</strong
  >
</p>
<p>
  text-transform: full-width
  <strong
    ><span
      >0123456789abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ!"#$%&()*+,-./:;<=>?@~</span
    ></strong
  >
</p>
```

[css]

```css
span {
  text-transform: full-width;
}
strong {
  width: 100%;
  float: right;
}
```

Some characters exist in two formats: normal width and a full-width,
with different Unicode code points. The full-width version is used to
mix them smoothly with Asian ideographic characters.

### Example using \"full-width\" (Japanese half-width katakana)

[html]

```html
<p>
  Initial String
  <strong>ｳｪﾌﾞﾌﾟﾛｸﾞﾗﾐﾝｸﾞの勉強</strong>
</p>
<p>
  text-transform: full-width
  <strong><span>ｳｪﾌﾞﾌﾟﾛｸﾞﾗﾐﾝｸﾞの勉強</span></strong>
</p>
```

[css]

```css
span {
  text-transform: full-width;
}
strong {
  width: 100%;
  float: right;
}
```

The Japanese half-width katakana was used to represent katakana in 8-bit
character codes. Unlike regular (full-width) katakana characters, a
letter with dakuten (voiced sound mark) is represented as two code
points, the body of letter and dakuten. The `full-width` combines these
into a single code point when converting these characters into
full-width.

### Example using \"full-size-kana\"

[html]

```html
<p>ァィゥェ ォヵㇰヶ ㇱㇲッㇳ ㇴㇵㇶㇷ ㇸㇹㇺャ ュョㇻㇼ ㇽㇾㇿヮ</p>
<p>ァィゥェ ォヵㇰヶ ㇱㇲッㇳ ㇴㇵㇶㇷ ㇸㇹㇺャ ュョㇻㇼ ㇽㇾㇿヮ</p>
</p>
```

[css]

```css
p:nth-of-type(2) {
  text-transform: full-size-kana;
}
```

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  text-transform]](https://drafts.csswg.org/css-text/#text-transform)

  -----------------------------------------------------------------------------

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

`text-transform`

1The `text-transform` property does not work for `::first-line`
pseudo-elements (nor for the one-colon syntax). See [Chromium bug
129669](https://crbug.com/129669).

12

1

4

7Since Opera 15, the `text-transform` property does not work for
`::first-line` pseudo-elements (nor for the one-colon syntax). See
[Chromium bug 129669](https://crbug.com/129669).

1The `text-transform` property does not work for `::first-line`
pseudo-elements (also not for the old one-colon syntax). See [WebKit bug
3409](https://webkit.org/b/3409).

4.4The `text-transform` property does not work for `::first-line`
pseudo-elements (nor for the one-colon syntax). See [Chromium bug
129669](https://crbug.com/129669).

18The `text-transform` property does not work for `::first-line`
pseudo-elements (nor for the one-colon syntax). See [Chromium bug
129669](https://crbug.com/129669).

4

11

1The `text-transform` property does not work for `::first-line`
pseudo-elements (also not for the old one-colon syntax). See [WebKit bug
3409](https://webkit.org/b/3409).

1.0The `text-transform` property does not work for `::first-line`
pseudo-elements (nor for the one-colon syntax). See [Chromium bug
129669](https://crbug.com/129669).

`capitalize`

1

12

1Before Firefox 14, some punctuation characters could interfere with
correct capitalization. See [bug 731536](https://bugzil.la/731536).

4

7

1

4.4

18

4Before Firefox 14, some punctuation characters could interfere with
correct capitalization. See [bug 731536](https://bugzil.la/731536).

11

1

1.0

`dutch_ij_digraph`

No

No

14

No

No

No

No

No

14

No

No

No

`full-size-kana`

No

No

64

No

No

17

No

No

64

No

17

No

`full-width`

No

No

19

No

No

17

No

No

19

No

17

No

`greek_accented_characters`

34

79

15

No

21

No

4.4

34

15

21

No

2.0

`lowercase_sigma`

30

12

14

4

17

6

4.4

30

14

18

6

2.0

`math-auto`

109

109

No

No

95

No

109

109

No

74

No

21.0

`turkic_is`

31

12

14

4

18

8

4.4.3

31

14

18

8

2.0

`uppercase_eszett`

1

18

1

No

7

1

4.4

18

4

11

1

1.0

See also
--------

- [`font-variant`](font-variant.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-transform>

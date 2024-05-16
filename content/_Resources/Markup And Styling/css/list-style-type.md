list-style-type
===============

The `list-style-type`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the marker (such as a disc, character, or custom counter style) of a
list item element.

Try it
------

The [color](color_value.md) of the marker will be the same as the computed
color of the element it applies to.

Only a few elements
([`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li)
and
[`<summary>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/summary))
have a default value of `display: list-item`. However, the
`list-style-type` property may be applied to any element whose
[`display`](display.md) value is set to `list-item`. Moreover, because this
property is inherited, it can be set on a parent element (commonly
[`<ol>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
or
[`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul))
to make it apply to all list items.

Syntax
------

[css]

```css
/* Partial list of types */
list-style-type: disc;
list-style-type: circle;
list-style-type: square;
list-style-type: decimal;
list-style-type: georgian;
list-style-type: trad-chinese-informal;
list-style-type: kannada;

/* <string> value */
list-style-type: "-";

/* Identifier matching an @counter-style rule */
list-style-type: custom-counter-style;

/* Keyword value */
list-style-type: none;

/* Global values */
list-style-type: inherit;
list-style-type: initial;
list-style-type: revert;
list-style-type: revert-layer;
list-style-type: unset;
```

The `list-style-type` property may be defined as any one of:

- a `<custom-ident>` value,
- a `symbols()` value,
- a `<string>` value, or
- the keyword `none`.

Note that:

- Some types require a suitable font installed to display as expected.
- The `cjk-ideographic` is identical to `trad-chinese-informal`; it
    exists for legacy reasons.

### Values

[`<custom-ident>`](custom-ident.md)

:   An identifier matching the value of a
    [`@counter-style`](@counter-style.md) or one of the predefined styles:

[`symbols()`](symbols.md)

:   Defines an anonymous style of the list.

[`<string>`](string.md)

:   The specified string will be used as the item\'s marker.

[`none`](#none)

:   No item marker is shown.

[`disc`](#disc)

:   A filled circle (default value).

[`circle`](#circle)

:   A hollow circle.

[`square`](#square)

:   A filled square.

[`decimal`](#decimal)

:   Decimal numbers, beginning with 1.

[`cjk-decimal`](#cjk-decimal)

:   Han decimal numbers.

[`decimal-leading-zero`](#decimal-leading-zero)

:   Decimal numbers, padded by initial zeros.

[`lower-roman`](#lower-roman)

:   Lowercase roman numerals.

[`upper-roman`](#upper-roman)

:   Uppercase roman numerals.

[`lower-greek`](#lower-greek)

:   Lowercase classical Greek.

[`lower-alpha`](#lower-alpha), `lower-latin`

:   Lowercase
    [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
    letters.

[`upper-alpha`](#upper-alpha), `upper-latin`

:   Uppercase ASCII letters.

[`arabic-indic`](#arabic-indic), `-moz-arabic-indic`

:   Arabic-Indic numbers.

[`armenian`](#armenian)

:   Traditional Armenian numbering.

[`bengali`](#bengali), `-moz-bengali`

:   Bengali numbering.

[`cambodian`](#cambodian)/`khmer`

:   Cambodian/Khmer numbering.

[`cjk-earthly-branch`](#cjk-earthly-branch), `-moz-cjk-earthly-branch`

:   Han \"Earthly Branch\" ordinals.

[`cjk-heavenly-stem`](#cjk-heavenly-stem), `-moz-cjk-heavenly-stem`

:   Han \"Heavenly Stem\" ordinals.

[`cjk-ideographic`](#cjk-ideographic)

:   Identical to `trad-chinese-informal`.

[`devanagari`](#devanagari), `-moz-devanagari`

:   Devanagari numbering.

[`ethiopic-numeric`](#ethiopic-numeric)

:   Ethiopic numbering.

[`georgian`](#georgian)

:   Traditional Georgian numbering.

[`gujarati`](#gujarati), `-moz-gujarati`

:   Gujarati numbering.

[`gurmukhi`](#gurmukhi), `-moz-gurmukhi`

:   Gurmukhi numbering.

[`hebrew`](#hebrew)

:   Traditional Hebrew numbering.

[`hiragana`](#hiragana)

:   Dictionary-order hiragana lettering.

[`hiragana-iroha`](#hiragana-iroha)

:   [Iroha-order](https://en.wikipedia.org/wiki/Iroha) hiragana
    lettering.

[`japanese-formal`](#japanese-formal)

:   Japanese formal numbering to be used in legal or financial
    documents. The kanjis are designed so that they can\'t be modified
    to look like another correct one.

[`japanese-informal`](#japanese-informal)

:   Japanese informal numbering.

[`kannada`](#kannada), `-moz-kannada`

:   Kannada numbering.

[`katakana`](#katakana)

:   Dictionary-order katakana lettering.

[`katakana-iroha`](#katakana-iroha)

:   [Iroha-order](https://en.wikipedia.org/wiki/Iroha) katakana
    lettering.

[`korean-hangul-formal`](#korean-hangul-formal)

:   Korean hangul numbering.

[`korean-hanja-formal`](#korean-hanja-formal)

:   Formal Korean Han numbering.

[`korean-hanja-informal`](#korean-hanja-informal)

:   Korean hanja numbering.

[`lao`](#lao), `-moz-lao`

:   Laotian numbering.

[`lower-armenian`](#lower-armenian)

:   Lowercase Armenian numbering.

[`malayalam`](#malayalam), `-moz-malayalam`

:   Malayalam numbering.

[`mongolian`](#mongolian)

:   Mongolian numbering.

[`myanmar`](#myanmar), `-moz-myanmar`

:   Myanmar (Burmese) numbering.

[`oriya`](#oriya), `-moz-oriya`

:   Oriya numbering.

[`persian`](#persian), `-moz-persian`

:   Persian numbering.

[`simp-chinese-formal`](#simp-chinese-formal)

:   Simplified Chinese formal numbering.

[`simp-chinese-informal`](#simp-chinese-informal)

:   Simplified Chinese informal numbering.

[`tamil`](#tamil), `-moz-tamil`

:   Tamil numbering.

[`telugu`](#telugu), `-moz-telugu`

:   Telugu numbering.

[`thai`](#thai), `-moz-thai`

:   Thai numbering.

[`tibetan`](#tibetan)

:   Tibetan numbering.

[`trad-chinese-formal`](#trad-chinese-formal)

:   Traditional Chinese formal numbering.

[`trad-chinese-informal`](#trad-chinese-informal)

:   Traditional Chinese informal numbering.

[`upper-armenian`](#upper-armenian)

:   Traditional uppercase Armenian numbering.

[`disclosure-open`](#disclosure-open)

:   Symbol indicating that a disclosure widget such as
    [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)
    is opened.

[`disclosure-closed`](#disclosure-closed)

:   Symbol indicating that a disclosure widget, like
    [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details)
    is closed.

Refer to the [All list style types](#all_list_style_types) example to
see the above values in action. Details of all the available counter
styles used by various cultures around the world can be found in
[Ready-made Counter
Styles](https://www.w3.org/TR/predefined-counter-styles/).

### Non-standard extensions

A few more predefined types are provided by Mozilla (Firefox), Blink
(Chrome and Opera) and WebKit (Safari) to support list types in other
languages. See the compatibility table to check which browsers support
which extension.

- `-moz-ethiopic-halehame`
- `-moz-ethiopic-halehame-am`
- `ethiopic-halehame-ti-er`, `-moz-ethiopic-halehame-ti-er`
- `ethiopic-halehame-ti-et`, `-moz-ethiopic-halehame-ti-et`
- `hangul`, `-moz-hangul`
- `hangul-consonant`, `-moz-hangul-consonant`
- `urdu`, `-moz-urdu`

Accessibility concerns
----------------------

Safari will not recognize an ordered or unordered list as a list in the
accessibility tree if it has a `list-style-type` value of `none`. To
learn more about this and potential workarounds, see
[`list-style`](list-style.md#accessibility_concerns).

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `disc`
  Applies to                         list items
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
list-style-type = 
  <counter-style>  |
  <string>         |
  none             

<counter-style> = 
  <counter-style-name>  |
  <symbols()>           

<symbols()> = 
  symbols( <symbols-type>? [ <string> | <image> ]+ )  

<symbols-type> = 
  cyclic      |
  numeric     |
  alphabetic  |
  symbolic    |
  fixed       

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Setting list item markers

#### HTML

[html]

```html
List 1
<ol class="normal">
  <li>Hello</li>
  <li>World</li>
  <li>What's up?</li>
</ol>

List 2
<ol class="shortcut">
  <li>Looks</li>
  <li>Like</li>
  <li>The</li>
  <li>Same</li>
</ol>
```

#### CSS

[css]

```css
ol.normal {
  list-style-type: upper-alpha;
}

/* or use the shortcut "list-style": */
ol.shortcut {
  list-style: upper-alpha;
}
```

#### Result

### All list style types

#### HTML

[html]

```html
<ol>
  <li>Apollo</li>
  <li>Hubble</li>
  <li>Chandra</li>
  <li>Cassini-Huygens</li>
  <li>Spitzer</li>
</ol>

<h2>Choose a list style type:</h2>

<div class="container">
  <label for="disc">
    <input type="radio" id="disc" name="type" value="disc" />disc
  </label>

  <label for="circle">
    <input type="radio" id="circle" name="type" value="circle" />circle
  </label>

  <label for="square">
    <input type="radio" id="square" name="type" value="square" />square
  </label>

  <label for="decimal">
    <input type="radio" id="decimal" name="type" value="decimal" />decimal
  </label>

  <label for="cjk-decimal">
    <input
      type="radio"
      id="cjk-decimal"
      name="type"
      value="cjk-decimal" />cjk-decimal
  </label>

  <label for="decimal-leading-zero">
    <input
      type="radio"
      id="decimal-leading-zero"
      name="type"
      value="decimal-leading-zero" />decimal-leading-zero
  </label>

  <label for="lower-roman">
    <input
      type="radio"
      id="lower-roman"
      name="type"
      value="lower-roman" />lower-roman
  </label>

  <label for="upper-roman">
    <input
      type="radio"
      id="upper-roman"
      name="type"
      value="upper-roman" />upper-roman
  </label>

  <label for="lower-greek">
    <input
      type="radio"
      id="lower-greek"
      name="type"
      value="lower-greek" />lower-greek
  </label>

  <label for="lower-alpha">
    <input
      type="radio"
      id="lower-alpha"
      name="type"
      value="lower-alpha" />lower-alpha, lower-latin
  </label>

  <label for="upper-alpha">
    <input
      type="radio"
      id="upper-alpha"
      name="type"
      value="upper-alpha" />upper-alpha, upper-latin
  </label>

  <label for="arabic-indic">
    <input
      type="radio"
      id="arabic-indic"
      name="type"
      value="arabic-indic" />arabic-indic
  </label>

  <label for="armenian">
    <input type="radio" id="armenian" name="type" value="armenian" />armenian
  </label>

  <label for="bengali">
    <input type="radio" id="bengali" name="type" value="bengali" />bengali
  </label>

  <label for="cambodian">
    <input type="radio" id="cambodian" name="type" value="cambodian" />cambodian
  </label>

  <label for="cjk-earthly-branch">
    <input
      type="radio"
      id="cjk-earthly-branch"
      name="type"
      value="cjk-earthly-branch" />cjk-earthly-branch
  </label>

  <label for="cjk-heavenly-stem">
    <input
      type="radio"
      id="cjk-heavenly-stem"
      name="type"
      value="cjk-heavenly-stem" />cjk-heavenly-stem
  </label>

  <label for="cjk-ideographic">
    <input
      type="radio"
      id="cjk-ideographic"
      name="type"
      value="cjk-ideographic" />cjk-ideographic
  </label>

  <label for="devanagari">
    <input
      type="radio"
      id="devanagari"
      name="type"
      value="devanagari" />devanagari
  </label>

  <label for="ethiopic-numeric">
    <input
      type="radio"
      id="ethiopic-numeric"
      name="type"
      value="ethiopic-numeric" />ethiopic-numeric
  </label>

  <label for="georgian">
    <input type="radio" id="georgian" name="type" value="georgian" />georgian
  </label>

  <label for="gujarati">
    <input type="radio" id="gujarati" name="type" value="gujarati" />gujarati
  </label>

  <label for="gurmukhi">
    <input type="radio" id="gurmukhi" name="type" value="gurmukhi" />gurmukhi
  </label>

  <label for="hebrew">
    <input type="radio" id="hebrew" name="type" value="hebrew" />hebrew
  </label>

  <label for="hiragana">
    <input type="radio" id="hiragana" name="type" value="hiragana" />hiragana
  </label>

  <label for="hiragana-iroha">
    <input
      type="radio"
      id="hiragana-iroha"
      name="type"
      value="hiragana-iroha" />hiragana-iroha
  </label>

  <label for="japanese-formal">
    <input
      type="radio"
      id="japanese-formal"
      name="type"
      value="japanese-formal" />japanese-formal
  </label>

  <label for="japanese-informal">
    <input
      type="radio"
      id="japanese-informal"
      name="type"
      value="japanese-informal" />japanese-informal
  </label>

  <label for="kannada">
    <input type="radio" id="kannada" name="type" value="kannada" />kannada
  </label>

  <label for="katakana">
    <input type="radio" id="katakana" name="type" value="katakana" />katakana
  </label>

  <label for="katakana-iroha">
    <input
      type="radio"
      id="katakana-iroha"
      name="type"
      value="katakana-iroha" />katakana-iroha
  </label>

  <label for="khmer">
    <input type="radio" id="khmer" name="type" value="khmer" />khmer
  </label>

  <label for="korean-hangul-formal">
    <input
      type="radio"
      id="korean-hangul-formal"
      name="type"
      value="korean-hangul-formal" />korean-hangul-formal
  </label>

  <label for="korean-hanja-formal">
    <input
      type="radio"
      id="korean-hanja-formal"
      name="type"
      value="korean-hanja-formal" />korean-hanja-formal
  </label>

  <label for="korean-hanja-informal">
    <input
      type="radio"
      id="korean-hanja-informal"
      name="type"
      value="korean-hanja-informal" />korean-hanja-informal
  </label>

  <label for="lao">
    <input type="radio" id="lao" name="type" value="lao" />lao
  </label>

  <label for="lower-armenian">
    <input
      type="radio"
      id="lower-armenian"
      name="type"
      value="lower-armenian" />lower-armenian
  </label>

  <label for="malayalam">
    <input type="radio" id="malayalam" name="type" value="malayalam" />malayalam
  </label>

  <label for="mongolian">
    <input type="radio" id="mongolian" name="type" value="mongolian" />mongolian
  </label>

  <label for="myanmar">
    <input type="radio" id="myanmar" name="type" value="myanmar" />myanmar
  </label>

  <label for="oriya">
    <input type="radio" id="oriya" name="type" value="oriya" />oriya
  </label>

  <label for="persian">
    <input type="radio" id="persian" name="type" value="persian" />persian
  </label>

  <label for="simp-chinese-formal">
    <input
      type="radio"
      id="simp-chinese-formal"
      name="type"
      value="simp-chinese-formal" />simp-chinese-formal
  </label>

  <label for="simp-chinese-informal">
    <input
      type="radio"
      id="simp-chinese-informal"
      name="type"
      value="simp-chinese-informal" />simp-chinese-informal
  </label>

  <label for="tamil">
    <input type="radio" id="tamil" name="type" value="tamil" />tamil
  </label>

  <label for="telugu">
    <input type="radio" id="telugu" name="type" value="telugu" />telugu
  </label>

  <label for="thai">
    <input type="radio" id="thai" name="type" value="thai" />thai
  </label>

  <label for="tibetan">
    <input type="radio" id="tibetan" name="type" value="tibetan" />tibetan
  </label>

  <label for="trad-chinese-formal">
    <input
      type="radio"
      id="trad-chinese-formal"
      name="type"
      value="trad-chinese-formal" />trad-chinese-formal
  </label>

  <label for="trad-chinese-informal">
    <input
      type="radio"
      id="trad-chinese-informal"
      name="type"
      value="trad-chinese-informal" />trad-chinese-informal
  </label>

  <label for="upper-armenian">
    <input
      type="radio"
      id="upper-armenian"
      name="type"
      value="upper-armenian" />upper-armenian
  </label>

  <label for="disclosure-open">
    <input
      type="radio"
      id="disclosure-open"
      name="type"
      value="disclosure-open" />disclosure-open
  </label>

  <label for="disclosure-closed">
    <input
      type="radio"
      id="disclosure-closed"
      name="type"
      value="disclosure-closed" />disclosure-closed
  </label>

  <label for="-moz-ethiopic-halehame">
    <input
      type="radio"
      id="-moz-ethiopic-halehame"
      name="type"
      value="-moz-ethiopic-halehame" />-moz-ethiopic-halehame
  </label>

  <label for="-moz-ethiopic-halehame-am">
    <input
      type="radio"
      id="-moz-ethiopic-halehame-am"
      name="type"
      value="-moz-ethiopic-halehame-am" />-moz-ethiopic-halehame-am
  </label>

  <label for="ethiopic-halehame-ti-er">
    <input
      type="radio"
      id="ethiopic-halehame-ti-er"
      name="type"
      value="ethiopic-halehame-ti-er" />ethiopic-halehame-ti-er
  </label>

  <label for="ethiopic-halehame-ti-et">
    <input
      type="radio"
      id="ethiopic-halehame-ti-et"
      name="type"
      value="ethiopic-halehame-ti-et" />ethiopic-halehame-ti-et
  </label>

  <label for="hangul">
    <input type="radio" id="hangul" name="type" value="hangul" />hangul
  </label>

  <label for="hangul-consonant">
    <input
      type="radio"
      id="hangul-consonant"
      name="type"
      value="hangul-consonant" />hangul-consonant
  </label>

  <label for="urdu">
    <input type="radio" id="urdu" name="type" value="urdu" />urdu
  </label>

  <label for="-moz-ethiopic-halehame-ti-er">
    <input
      type="radio"
      id="-moz-ethiopic-halehame-ti-er"
      name="type"
      value="-moz-ethiopic-halehame-ti-er" />-moz-ethiopic-halehame-ti-er
  </label>

  <label for="-moz-ethiopic-halehame-ti-et">
    <input
      type="radio"
      id="-moz-ethiopic-halehame-ti-et"
      name="type"
      value="-moz-ethiopic-halehame-ti-et" />-moz-ethiopic-halehame-ti-et
  </label>

  <label for="-moz-hangul">
    <input
      type="radio"
      id="-moz-hangul"
      name="type"
      value="-moz-hangul" />-moz-hangul
  </label>

  <label for="-moz-hangul-consonant">
    <input
      type="radio"
      id="-moz-hangul-consonant"
      name="type"
      value="-moz-hangul-consonant" />-moz-hangul-consonant
  </label>

  <label for="-moz-urdu">
    <input type="radio" id="-moz-urdu" name="type" value="-moz-urdu" />-moz-urdu
  </label>
</div>
```

#### CSS

[css]

```css
ol {
  font-size: 1.2rem;
}

.container {
  column-count: 3;
}

label {
  display: block;
}

input {
  margin: 0.4rem;
}
```

#### JavaScript

[js]

```js
const container = document.querySelector(".container");
container.addEventListener("change", (event) => {
  const list = document.querySelector("ol");
  list.setAttribute("style", `list-style-type: $`);
});
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Lists and Counters Module Level 3\
  [\# text-markers]](https://drafts.csswg.org/css-lists/#text-markers)

[CSS Counter Styles Level 3\
  [\#
  extending-css2]](https://drafts.csswg.org/css-counter-styles/#extending-css2)
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

`list-style-type`

1

12

1

4

3.5

1

≤37

18

4

10.1

1

1.0

`afar`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`amharic`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`amharic-abegede`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`arabic-indic`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`armenian`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`asterisks`

9113--45

91

No

No

7715--32

5.1

914.4--45

9118--45

No

6414--32

5

16.01.0--5.0

`bengali`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`binary`

9113--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`cambodian`

6

79

33

No

15

5

4.4

18

33

14

4.2

1.0

`circle`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`cjk-decimal`

91

91

28

No

77

15

91

91

28

64

15

16.0

`cjk-earthly-branch`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`cjk-heavenly-stem`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`cjk-ideographic`

1

79

1

No

15

7Until version 15, only decimal numbers display.

5

4.4

18

4

14

10.1Until version 15, only decimal numbers display.

4.2

1.0

`decimal`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`decimal-leading-zero`

1

12

1

8

8

1

4.4

18

4

10.1

1

1.0

`devanagari`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`disc`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`disclosure-closed`

89

89

33

No

75

15

89

89

33

63

15

15.0

`disclosure-open`

89

89

33

No

75

15

89

89

33

63

15

15.0

`ethiopic`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-abegede`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-abegede-am-et`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-abegede-gez`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-abegede-ti-er`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-abegede-ti-et`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame`

45

79

1

No

32

17

45

45

4

32

17

5.0

`ethiopic-halehame-aa-er`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame-aa-et`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame-am`

45

79

1

No

32

17

45

45

4

32

17

5.0

`ethiopic-halehame-am-et`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame-gez`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame-om-et`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame-sid-et`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame-so-et`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-halehame-ti-er`

6

79

1

No

15

5

3

18

4

14

4.2

1.0

`ethiopic-halehame-ti-et`

6

79

1

No

15

5

3

18

4

14

4.2

1.0

`ethiopic-halehame-tig`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`ethiopic-numeric`

91

91

33Before Firefox 38, Firefox added a dot as suffix of the number for
`ethiopic-numeric` (for example, ፫. instead of ፫). The specification
later defined the absence of a suffix, which Firefox 38 followed.

1

No

77

15

91

91

33Before Firefox 38, Firefox added a dot as suffix of the number for
`ethiopic-numeric` (for example, ፫. instead of ፫). The specification
later defined the absence of a suffix, which Firefox 38 followed.

4

64

15

16.0

`footnotes`

9113--45

91

No

No

7715--32

5.1

914.4--45

9118--45

No

6414--32

5

16.01.0--5.0

`georgian`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`gujarati`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`gurmukhi`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`hangul`

6

79

1

No

15

5

4.4

18

4

14

4.2

1.0

`hangul-consonant`

6

79

1

No

15

5

4.4

18

4

14

4.2

1.0

`hebrew`

1

79

1

No

15

1

4.4

18

4

14

1

1.0

`hiragana`

1

79

1

No

15

1

4.4

18

4

14

1

1.0

`hiragana-iroha`

1

79

1

No

15

1

4.4

18

4

14

1

1.0

`japanese-formal`

91

91

281

No

77

15

91

91

284

64

15

16.0

`japanese-informal`

91

91

281

No

77

15

91

91

284

64

15

16.0

`kannada`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`katakana`

1

79

1

No

15

1

4.4

18

4

14

1

1.0

`katakana-iroha`

1

79

1

No

15

1

4.4

18

4

14

1

1.0

`khmer`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`korean-hangul-formal`

45

79

28

No

32

15

45

45

28

32

15

5.0

`korean-hanja-formal`

45

79

28

No

32

15

45

45

28

32

15

5.0

`korean-hanja-informal`

45

79

28

No

32

15

45

45

28

32

15

5.0

`lao`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`lower-alpha`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`lower-armenian`

13

79

33

No

15

5.1

4.4

18

33

14

5

1.0

`lower-greek`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`lower-hexadecimal`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`lower-latin`

1

12

1

8

6

1

4.4

18

4

10.1

1

5.0

`lower-norwegian`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`lower-roman`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`malayalam`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`mongolian`

6

79

33

No

15

5

4.4

18

33

14

4.2

1.0

`myanmar`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`octal`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`oriya`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`oromo`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`persian`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`sidama`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`simp-chinese-formal`

45

79

281

No

32

15

45

45

284

32

15

5.0

`simp-chinese-informal`

45

79

281

No

32

15

45

45

284

32

15

5.0

`somali`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`square`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`string`

79

79

39

No

66

14.1

79

79

39

57

14.5

12.0

`symbols`

No

No

35

No

No

No

No

No

35

No

No

No

`tamil`

91

91

331

No

77

15

91

91

334

64

15

16.0

`telugu`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`thai`

6

79

331

No

15

5

4.4

18

334

14

4.2

1.0

`tibetan`

6

79

33

No

15

5

4.4

18

No

14

4.2

1.0

`tigre`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`tigrinya-er`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`tigrinya-er-abegede`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`tigrinya-et`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`tigrinya-et-abegede`

916--45

91

No

No

7715--32

5

914.4--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`trad-chinese-formal`

45

79

281

No

32

15

45

45

284

32

15

5.0

`trad-chinese-informal`

45

79

281

No

32

15

45

45

284

32

15

5.0

`upper-alpha`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`upper-armenian`

13

79

33

No

15

5.1

4.4

18

33

14

5

1.0

`upper-greek`

911--45

9112--79

No

8

6

1

914.4--45

9118--45

No

10.1

1

16.01.0--5.0

`upper-hexadecimal`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`upper-latin`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`upper-norwegian`

916--45

91

No

No

7715--32

5

3--45

9118--45

No

6414--32

4.2

16.01.0--5.0

`upper-roman`

1

12

1

8

6

1

4.4

18

4

10.1

1

1.0

`urdu`

6

79

33

No

15

5

4.4

18

33

14

4.2

1.0

See also
--------

- [`list-style`](list-style.md), [`list-style-image`](list-style-image.md),
    [`list-style-position`](list-style-position.md)
- [Counter styles converter](https://r12a.github.io/app-counters/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/list-style-type>

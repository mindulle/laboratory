word-break
==========

The `word-break` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets whether line breaks appear wherever the text would
otherwise overflow its content box.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
word-break: normal;
word-break: break-all;
word-break: keep-all;
word-break: break-word; /* deprecated */

/* Global values */
word-break: inherit;
word-break: initial;
word-break: revert;
word-break: revert-layer;
word-break: unset;
```

The `word-break` property is specified as a single keyword chosen from
the list of values below.

### Values

[`normal`](#normal)

:   Use the default line break rule.

[`break-all`](#break-all)

:   To prevent overflow, word breaks should be inserted between any two
    characters (excluding Chinese/Japanese/Korean text).

[`keep-all`](#keep-all)

:   Word breaks should not be used for Chinese/Japanese/Korean (CJK)
    text. Non-CJK text behavior is the same as for `normal`.

[`break-word`](#break-word) [Deprecated]

:   Has the same effect as `overflow-wrap: anywhere` combined with
    `word-break: normal`, regardless of the actual value of the
    [`overflow-wrap`](overflow-wrap.md) property.

**Note:** In contrast to `word-break: break-word` and
`overflow-wrap: break-word` (see [`overflow-wrap`](overflow-wrap.md)),
`word-break: break-all` will create a break at the exact place where
text would otherwise overflow its container (even if putting an entire
word on its own line would negate the need for a break).

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
word-break = 
  normal      |
  keep-all    |
  break-all   |
  break-word  
```

Examples
--------

### HTML

[html]

```html
<p>1. <code>word-break: normal</code></p>
<p class="normal narrow">
  This is a long and Honorificabilitudinitatibus califragilisticexpialidocious
  Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
  グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉
</p>

<p>2. <code>word-break: break-all</code></p>
<p class="breakAll narrow">
  This is a long and Honorificabilitudinitatibus califragilisticexpialidocious
  Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
  グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉
</p>

<p>3. <code>word-break: keep-all</code></p>
<p class="keepAll narrow">
  This is a long and Honorificabilitudinitatibus califragilisticexpialidocious
  Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
  グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉
</p>

<p>4. <code>word-break: break-word</code></p>
<p class="breakWord narrow">
  This is a long and Honorificabilitudinitatibus califragilisticexpialidocious
  Taumatawhakatangihangakoauauotamateaturipukakapikimaungahoronukupokaiwhenuakitanatahu
  グレートブリテンおよび北アイルランド連合王国という言葉は本当に長い言葉
</p>
```

### CSS

[css]

```css
.narrow {
  padding: 10px;
  border: 1px solid;
  width: 500px;
  margin: 0 auto;
  font-size: 20px;
  line-height: 1.5;
  letter-spacing: 1px;
}

.normal {
  word-break: normal;
}

.breakAll {
  word-break: break-all;
}

.keepAll {
  word-break: keep-all;
}

.breakWord {
  word-break: break-word;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  word-break-property]](https://drafts.csswg.org/css-text/#word-break-property)

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

`word-break`

1

12

15

8Don\'t use `-ms-word-break`, which is a synonym for `word-break`.

5.5No version of Internet Explorer supports the `initial` value.

15

3

≤37

18

15

14

2

1.0

`break-word`

1

79

67

No

15

3

≤37

18

67

14

2

1.0

`keep-all`

44

12

15

5.5

31

9

44

44

15

32

9

4.0

See also
--------

- [`overflow-wrap`](overflow-wrap.md)
- [`hyphens`](hyphens.md)
- [`line-break`](line-break.md)
- [](wrapping_breaking_text.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/word-break>

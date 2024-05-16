font-variant-east-asian
=======================

The `font-variant-east-asian` CSS property controls the use of alternate
glyphs for East Asian scripts, like Japanese and Chinese.

Try it
------

Syntax
------

[css]

```css
font-variant-east-asian: normal;
font-variant-east-asian: ruby;
font-variant-east-asian: jis78; /* <east-asian-variant-values> */
font-variant-east-asian: jis83; /* <east-asian-variant-values> */
font-variant-east-asian: jis90; /* <east-asian-variant-values> */
font-variant-east-asian: jis04; /* <east-asian-variant-values> */
font-variant-east-asian: simplified; /* <east-asian-variant-values> */
font-variant-east-asian: traditional; /* <east-asian-variant-values> */
font-variant-east-asian: full-width; /* <east-asian-width-values> */
font-variant-east-asian: proportional-width; /* <east-asian-width-values> */
font-variant-east-asian: ruby full-width jis83;

/* Global values */
font-variant-east-asian: inherit;
font-variant-east-asian: initial;
font-variant-east-asian: revert;
font-variant-east-asian: revert-layer;
font-variant-east-asian: unset;
```

### Values

[`normal`](#normal)

:   This keyword leads to the deactivation of the use of such alternate
    glyphs.

[`ruby`](#ruby)

:   This keyword forces the use of special glyphs for ruby characters.
    As these are usually smaller, font creators often designs specific
    forms, usually slightly bolder to improve the contrast. This keyword
    corresponds to the OpenType values `ruby`.

[`<east-asian-variant-values>`](#east-asian-variant-values)

:   These values specify a set of logographic glyph variants which
    should be used for display. Possible values are:

      Keyword         Standard defining the glyphs                                                  OpenType equivalent
      --------------- ----------------------------------------------------------------------------- ---------------------
      `jis78`         [JIS X 0208:1978](https://en.wikipedia.org/wiki/JIS_X_0208#First_standard)    `jp78`
      `jis83`         [JIS X 0208:1983](https://en.wikipedia.org/wiki/JIS_X_0208#Second_standard)   `jp83`
      `jis90`         [JIS X 0208:1990](https://en.wikipedia.org/wiki/JIS_X_0208#Third_standard)    `jp90`
      `jis04`         [JIS X 0213:2004](https://en.wikipedia.org/wiki/JIS_X_0213)                   `jp04`
      `simplified`    None, use the simplified Chinese glyphs                                       `smpl`
      `traditional`   None, use the traditional Chinese glyphs                                      `trad`

[`<east-asian-width-values>`](#east-asian-width-values)

:   These values control the sizing of figures used for East Asian
    characters. Two values are possible:

    -   `proportional-width` activating the set of East Asian characters
        which vary in width. It corresponds to the OpenType values
        `pwid`.
    -   `full-width` activating the set of East Asian characters which
        are all of the same, roughly square, width metric. It
        corresponds to the OpenType values `fwid`.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-variant-east-asian = 
  normal                                              |
  [ <east-asian-variant-values> || <east-asian-width-values> || ruby ]  

<east-asian-variant-values> = 
  jis78        |
  jis83        |
  jis90        |
  jis04        |
  simplified   |
  traditional  

<east-asian-width-values> = 
  full-width          |
  proportional-width  
```

Examples
--------

### Setting East Asian glyph variants

This example require font \"Yu Gothic\" installed in your OS, other
fonts may not support OpenType features.

#### HTML

[html]

```html
<table>
  <thead></thead>
  <tbody style="border:0;">
    <tr>
      <th>normal/jis78:</th>
      <td>麹町</td>
      <td class="jis78">麹町</td>
    </tr>
    <tr>
      <th>normal/ruby:</th>
      <td>しんかんせん</td>
      <td class="ruby">しんかんせん</td>
    </tr>
    <tr>
      <th>normal/traditional:</th>
      <td>大学</td>
      <td class="traditional">大学</td>
    </tr>
  </tbody>
</table>
```

#### CSS

[css]

```css
td {
  font-family: "Yu Gothic";
  font-size: 20px;
}
th {
  color: grey;
  padding-right: 10px;
}

.ruby {
  font-variant-east-asian: ruby;
}

.jis78 {
  font-variant-east-asian: jis78;
}

.traditional {
  font-variant-east-asian: traditional;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variant-east-asian-prop]](https://drafts.csswg.org/css-fonts/#font-variant-east-asian-prop)

  ----------------------------------------------------------------------------------------------------------

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

`font-variant-east-asian`

63

79

34

No

50

9.1

63

63

34

46

9.3

8.0

See also
--------

- [`font-variant`](font-variant.md)
- [`font-variant-alternates`](font-variant-alternates.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-numeric`](font-variant-numeric.md)
- [`font-variant-position`](font-variant-position.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-east-asian>

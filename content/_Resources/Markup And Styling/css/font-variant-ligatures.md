font-variant-ligatures
======================

The `font-variant-ligatures` CSS property controls which
[ligatures](https://developer.mozilla.org/en-US/docs/Glossary/Ligature)
and [contextual forms] are used in textual content of
the elements it applies to. This leads to more harmonized forms in the
resulting text.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
font-variant-ligatures: normal;
font-variant-ligatures: none;
font-variant-ligatures: common-ligatures; /* <common-lig-values> */
font-variant-ligatures: no-common-ligatures; /* <common-lig-values> */
font-variant-ligatures: discretionary-ligatures; /* <discretionary-lig-values> */
font-variant-ligatures: no-discretionary-ligatures; /* <discretionary-lig-values> */
font-variant-ligatures: historical-ligatures; /* <historical-lig-values> */
font-variant-ligatures: no-historical-ligatures; /* <historical-lig-values> */
font-variant-ligatures: contextual; /* <contextual-alt-values> */
font-variant-ligatures: no-contextual; /* <contextual-alt-values> */

/* Global values */
font-variant-ligatures: inherit;
font-variant-ligatures: initial;
font-variant-ligatures: revert;
font-variant-ligatures: revert-layer;
font-variant-ligatures: unset;
```

The `font-variant-ligatures` property is specified as one of the keyword
values listed below.

### Values

[`normal`](#normal)

:   This keyword leads to the activation of the usual ligatures and
    contextual forms needed for correct rendering. The ligatures and
    forms activated depend on the font, language and kind of script.
    This is the default value.

[`none`](#none)

:   This keyword specifies that all ligatures and contextual forms are
    disabled, even common ones.

[*`<common-lig-values>`*](#common-lig-values)

:   These values control the most common ligatures, like for `fi`,
    `ffi`, `th` or similar. They correspond to the OpenType values
    `liga` and `clig`. Two values are possible:

    -   `common-ligatures` activating these ligatures. Note that the
        keyword `normal` activates these ligatures.
    -   `no-common-ligatures` deactivating these ligatures.

[*`<discretionary-lig-values>`*](#discretionary-lig-values)

:   These values control specific ligatures, specific to the font and
    defined by the type designer. They correspond to the OpenType values
    `dlig`. Two values are possible:

    -   `discretionary-ligatures` activating these ligatures.
    -   `no-discretionary-ligatures` deactivating the ligatures. Note
        that the keyword `normal` usually deactivates these ligatures.

[*`<historical-lig-values>`*](#historical-lig-values)

:   These values control the ligatures used historically, in old books,
    like the German tz digraph being displayed as ꜩ. They correspond to
    the OpenType values `hlig`. Two values are possible:

    -   `historical-ligatures` activating these ligatures.
    -   `no-historical-ligatures` deactivating the ligatures. Note that
        the keyword `normal` usually deactivates these ligatures.

[*`<contextual-alt-values>`*](#contextual-alt-values)

:   These values control whether letters adapt to their context---that
    is, whether they adapt to the surrounding letters. These values
    correspond to the OpenType values `calt`. Two values are possible:

    -   `contextual` specifies that the contextual alternates are to be
        used. Note that the keyword `normal` usually activates these
        ligatures too.
    -   `no-contextual` prevents their use.

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
font-variant-ligatures = 
  normal                                              |
  none                                                |
  [ <common-lig-values> || <discretionary-lig-values> || <historical-lig-values> || <contextual-alt-values> ]  

<common-lig-values> = 
  common-ligatures     |
  no-common-ligatures  

<discretionary-lig-values> = 
  discretionary-ligatures     |
  no-discretionary-ligatures  

<historical-lig-values> = 
  historical-ligatures     |
  no-historical-ligatures  

<contextual-alt-values> = 
  contextual     |
  no-contextual  
```

Examples
--------

### Setting font ligatures and contextual forms

#### HTML

[html]

```html
<link href="//fonts.googleapis.com/css?family=Lora" rel="stylesheet" />
<p class="normal">
  normal<br />
  if fi ff tf ft jf fj
</p>
<p class="none">
  none<br />
  if fi ff tf ft jf fj
</p>
<p class="common-ligatures">
  common-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="no-common-ligatures">
  no-common-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="discretionary-ligatures">
  discretionary-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="no-discretionary-ligatures">
  no-discretionary-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="historical-ligatures">
  historical-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="no-historical-ligatures">
  no-historical-ligatures<br />
  if fi ff tf ft jf fj
</p>
<p class="contextual">
  contextual<br />
  if fi ff tf ft jf fj
</p>
<p class="no-contextual">
  no-contextual<br />
  if fi ff tf ft jf fj
</p>
```

#### CSS

[css]

```css
p {
  font-family: Lora, serif;
}
.normal {
  font-variant-ligatures: normal;
}

.none {
  font-variant-ligatures: none;
}

.common-ligatures {
  font-variant-ligatures: common-ligatures;
}

.no-common-ligatures {
  font-variant-ligatures: no-common-ligatures;
}

.discretionary-ligatures {
  font-variant-ligatures: discretionary-ligatures;
}

.no-discretionary-ligatures {
  font-variant-ligatures: no-discretionary-ligatures;
}

.historical-ligatures {
  font-variant-ligatures: historical-ligatures;
}

.no-historical-ligatures {
  font-variant-ligatures: no-historical-ligatures;
}

.contextual {
  font-variant-ligatures: contextual;
}

.no-contextual {
  font-variant-ligatures: no-contextual;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variant-ligatures-prop]](https://drafts.csswg.org/css-fonts/#font-variant-ligatures-prop)

  --------------------------------------------------------------------------------------------------------

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

`font-variant-ligatures`

3431

7979

34

No

2119

9.17

374.4

34

34

2119

9.37

2.0

See also
--------

- [`font-variant`](font-variant.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-numeric`](font-variant-numeric.md)
- [`font-variant-position`](font-variant-position.md)
- [CSS fonts module](css_fonts.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-ligatures>

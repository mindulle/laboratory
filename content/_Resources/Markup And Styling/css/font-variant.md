font-variant
============

The `font-variant` CSS [shorthand property](shorthand_properties.md) allows
you to set all the font variants for a font.

You can also set the `<font-variant-css2>` values of `font-variant`
defined in CSS Level 2.1, (that is, `normal` or `small-caps`), by using
the [`font`](font.md) shorthand.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`font-variant-alternates`](font-variant-alternates.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-numeric`](font-variant-numeric.md)
- [`font-variant-position`](font-variant-position.md)

Syntax
------

[css]

```css
font-variant: small-caps;
font-variant: common-ligatures small-caps;

/* Global values */
font-variant: inherit;
font-variant: initial;
font-variant: revert;
font-variant: revert-layer;
font-variant: unset;
```

### Values

[`normal`](#normal)

:   Specifies a normal font face. Each longhand property has an initial
    value of `normal`.

[`none`](#none)

:   Sets the value of the
    [`font-variant-ligatures`](font-variant-ligatures.md) as `none` and the
    values of the other longhand properties as `normal`, their initial
    value.

[`<common-lig-values>`](#common-lig-values), `<discretionary-lig-values>`, `<historical-lig-values>`, `<contextual-alt-values>`

:   Specifies the keywords related to the
    [`font-variant-ligatures`](font-variant-ligatures.md) longhand
    property. The possible values are `common-ligatures`,
    `no-common-ligatures`, `discretionary-ligatures`,
    `no-discretionary-ligatures`, `historical-ligatures`,
    `no-historical-ligatures`, `contextual`, and `no-contextual`.

[`stylistic()`](#stylistic), `historical-forms`, `styleset()`, `character-variant()`, `swash()`, `ornaments()`, `annotation()`

:   Specifies the keywords and functions related to the
    [`font-variant-ligatures`](font-variant-ligatures.md) longhand
    property.

[`small-caps`](#small-caps), `all-small-caps`, `petite-caps`, `all-petite-caps`, `unicase`, `titling-caps`

:   Specifies the keywords and functions related to the
    [`font-variant-caps`](font-variant-caps.md) longhand property. The
    `small-caps` value is the only non-`normal` font variant valid
    within the [`font`](font.md) shorthand property.

[`<numeric-figure-values>`](#numeric-figure-values), `<numeric-spacing-values>`, `<numeric-fraction-values>`, `ordinal`, `slashed-zero`

:   Specifies the keywords related to the
    [`font-variant-numeric`](font-variant-numeric.md) longhand property.
    The possible values are `lining-nums`, `oldstyle-nums`,
    `proportional-nums`, `tabular-nums`, `diagonal-fractions`,
    `stacked-fractions`, `ordinal`, and `slashed-zero`.

[`<east-asian-variant-values>`](#east-asian-variant-values), `<east-asian-width-values>`, `ruby`

:   Specifies the keywords related to the
    [`font-variant-east-asian`](font-variant-east-asian.md) longhand
    property. The possible values are `jis78`, `jis83`, `jis90`,
    `jis04`, `simplified`, `traditional`, `full-width`,
    `proportional-width`, and `ruby`.

[`sub`](#sub), `super`

:   Specifies the keywords and functions related to the
    [`font-variant-position`](font-variant-position.md) longhand property.

[`text`](#text), `emoji`, `unicode`

:   Specifies the keywords and functions related to the
    [`font-variant-emoji`](font-variant-emoji.md) longhand property.

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

```text
font-variant = 
  normal                                              |
  none                                                |
  [ [ <common-lig-values> || <discretionary-lig-values> || <historical-lig-values> || <contextual-alt-values> ] || [ small-caps | all-small-caps | petite-caps | all-petite-caps | unicase | titling-caps ] || [ stylistic( <feature-value-name> ) || historical-forms || styleset( <feature-value-name># ) || character-variant( <feature-value-name># ) || swash( <feature-value-name> ) || ornaments( <feature-value-name> ) || annotation( <feature-value-name> ) ] || [ <numeric-figure-values> || <numeric-spacing-values> || <numeric-fraction-values> || ordinal || slashed-zero ] || [ <east-asian-variant-values> || <east-asian-width-values> || ruby ] || [ sub | super ] || [ text | emoji | unicode ] ]  

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

<feature-value-name> = 
  <ident>  

<numeric-figure-values> = 
  lining-nums    |
  oldstyle-nums  

<numeric-spacing-values> = 
  proportional-nums  |
  tabular-nums       

<numeric-fraction-values> = 
  diagonal-fractions  |
  stacked-fractions   

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

### Setting the small-caps font variant

#### HTML

[html]

```html
<p class="normal">Firefox rocks!</p>
<p class="small">Firefox rocks!</p>
```

#### CSS

[css]

```css
p.normal {
  font-variant: normal;
}
p.small {
  font-variant: small-caps;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-variant-prop]](https://drafts.csswg.org/css-fonts/#font-variant-prop)

  ------------------------------------------------------------------------------------

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

`font-variant`

1

12

1

4Only supports the `small-caps` and `normal` keywords.

3.5

1

4.4

18

4

11

1

1.0

`css_fonts_shorthand`

52

79

34

No

39

9.1

52

52

34

41

9.3

6.0

`font-variant-emoji`

No

No

108

No

No

No

No

No

108

No

No

No

`greek_accented_characters`

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

No

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

No

NoSome operating systems may correctly omit accents in all-uppercase
Greek.

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

No

NoSome operating systems may correctly omit accents in all-uppercase
Greek text.

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

NoSome operating systems may capitalize `ß` as `SS`.

NoSome operating systems may capitalize `ß` as `SS`.

NoSome operating systems may capitalize `ß` as `SS`.

No

NoSome operating systems may capitalize `ß` as `SS`.

No

NoSome operating systems may capitalize `ß` as `SS`.

NoSome operating systems may capitalize `ß` as `SS`.

NoSome operating systems may capitalize `ß` as `SS`.

NoSome operating systems may capitalize `ß` as `SS`.

No

NoSome operating systems may capitalize `ß` as `SS`.

See also
--------

- [`text-transform`](text-transform.md)
- [`text-combine-upright`](text-combine-upright.md)
- [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant>

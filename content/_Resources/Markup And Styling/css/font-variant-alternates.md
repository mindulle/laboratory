font-variant-alternates
=======================

The `font-variant-alternates` CSS property controls the usage of
alternate glyphs. These alternate glyphs may be referenced by
alternative names defined in
[`@font-feature-values`](@font-feature-values.md).

The [`@font-feature-values`](@font-feature-values.md) at-rule can be used
to associate, for a given font face, a human-readable name with a
numeric index that controls a particular OpenType font feature. For
features that select alternative glyphs (`stylistic`, `styleset`,
`character-variant`, `swash`, `ornament` or `annotation`), the
`font-variant-alternates` property can then reference the human-readable
name in order to apply the associated feature.

This allows CSS rules to enable alternative glyphs without needing to
know the specific index values that a particular font uses to control
them.

Syntax
------

[css]

```css
/* Keyword values */
font-variant-alternates: normal;
font-variant-alternates: historical-forms;

/* Functional notation values */
font-variant-alternates: stylistic(user-defined-ident);
font-variant-alternates: styleset(user-defined-ident);
font-variant-alternates: character-variant(user-defined-ident);
font-variant-alternates: swash(user-defined-ident);
font-variant-alternates: ornaments(user-defined-ident);
font-variant-alternates: annotation(user-defined-ident);
font-variant-alternates: swash(ident1) annotation(ident2);

/* Global values */
font-variant-alternates: inherit;
font-variant-alternates: initial;
font-variant-alternates: revert;
font-variant-alternates: revert-layer;
font-variant-alternates: unset;
```

This property may take one of two forms:

- either the keyword `normal`
- or one or more of the other keywords and functions listed below,
    space-separated, in any order.

### Values

[`normal`](#normal)

:   This keyword deactivates alternate glyphs.

[`historical-forms`](#historical-forms)

:   This keyword enables historical forms --- glyphs that were common in
    the past but not today. It corresponds to the OpenType value `hist`.

#### stylistic()

:   This function enables stylistic alternates for individual
    characters. The parameter is a font-specific name mapped to a
    number. It corresponds to the OpenType value `salt`, like `salt 2`.

#### styleset()

:   This function enables stylistic alternatives for sets of characters.
    The parameter is a font-specific name mapped to a number. It
    corresponds to the OpenType value `ssXY`, like `ss02`.

#### character-variant()

:   This function enables specific stylistic alternatives for
    characters. It is similar to `styleset()`, but doesn\'t create
    coherent glyphs for a set of characters; individual characters will
    have independent and not necessarily coherent styles. The parameter
    is a font-specific name mapped to a number. It corresponds to the
    OpenType value `cvXY`, like `cv02`.

#### swash()

:   This function enables
    [swash](https://en.wikipedia.org/wiki/Swash_%28typography%29)
    glyphs. The parameter is a font-specific name mapped to a number. It
    corresponds to the OpenType values `swsh` and `cswh`, like `swsh 2`
    and `cswh 2`.

[`ornaments()`](#ornaments)

:   This function enables ornaments, like
    [fleurons](https://en.wikipedia.org/wiki/Fleuron_%28typography%29)
    and other dingbat glyphs. The parameter is a font-specific name
    mapped to a number. It corresponds to the OpenType value `ornm`,
    like `ornm 2`.

    **Note:** In order to preserve text semantics, font designers should
    include ornaments that don\'t match Unicode dingbat characters as
    ornamental variants of the bullet character (U+2022). Be aware that
    some existing fonts don\'t follow this advice.

#### annotation()

:   This function enables annotations, like circled digits or inverted
    characters. The parameter is a font-specific name mapped to a
    number. It corresponds to the OpenType value `nalt`, like `nalt 2`.

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
font-variant-alternates = 
  normal                                              |
  [ stylistic( <feature-value-name> ) || historical-forms || styleset( <feature-value-name># ) || character-variant( <feature-value-name># ) || swash( <feature-value-name> ) || ornaments( <feature-value-name> ) || annotation( <feature-value-name> ) ]  

<feature-value-name> = 
  <ident>  
```

Examples
--------

### Enabling swash glyphs

In this example, we use the `@font-feature-values` at-rule to define a
name for the `swash` feature of the
[MonteCarlo](https://github.com/googlefonts/monte-carlo) font. The rule
maps the name `"fancy"` to the index value `1`.

We can then use that name inside `font-variant-alternates` to switch on
swashes for that font. This is the equivalent of a line like
`font-feature-settings: "swsh" 1`, except that the CSS applying the
feature does not need to include, or even know, the index value needed
for this particular font.

#### HTML

[html]

```html
<p>A Fancy Swash</p>
<p class="variant">A Fancy Swash</p>
```

#### CSS

[css]

```css
@font-face {
  font-family: MonteCarlo;
  src: url("montecarlo-regular.woff2");
}

@font-feature-values "MonteCarlo" {
  @swash {
    fancy: 1;
  }
}

p {
  font-family: "MonteCarlo";
  font-size: 3rem;
  margin: 0.7rem 3rem;
}

.variant {
  font-variant-alternates: swash(fancy);
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
  font-variant-alternates-prop]](https://drafts.csswg.org/css-fonts/#font-variant-alternates-prop)

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

`font-variant-alternates`

111

111

34

No

97

9.1

111

111

34

No

9.3

22.0

`annotation`

111

111

34

No

97

16.2

111

111

34

No

16.2

22.0

`character_variant`

111

111

34

No

97

16.2

111

111

34

No

16.2

22.0

`ornaments`

111

111

34

No

97

16.2

111

111

34

No

16.2

22.0

`styleset`

111

111

34

No

97

16.2

111

111

34

No

16.2

22.0

`stylistic`

111

111

34

No

97

16.2

111

111

34

No

16.2

22.0

`swash`

111

111

34

No

97

16.2

111

111

34

No

16.2

22.0

See also
--------

- [`font-variant`](font-variant.md)
- [`font-variant-caps`](font-variant-caps.md)
- [`font-variant-east-asian`](font-variant-east-asian.md)
- [`font-variant-emoji`](font-variant-emoji.md)
- [`font-variant-ligatures`](font-variant-ligatures.md)
- [`font-variant-numeric`](font-variant-numeric.md)
- [`font-variant-position`](font-variant-position.md)
- [`@font-feature-values`](@font-feature-values.md)
- [`font-feature-settings`](_Resources/Markup%20And%20Styling/css/font-feature-settings.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant-alternates>

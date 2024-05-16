letter-spacing
==============

The `letter-spacing`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the horizontal spacing behavior between text characters. This value is
added to the natural spacing between characters while rendering the
text. Positive values of `letter-spacing` causes characters to spread
farther apart, while negative values of `letter-spacing` bring
characters closer together.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
letter-spacing: normal;

/* <length> values */
letter-spacing: 0.3em;
letter-spacing: 3px;
letter-spacing: 0.3px;

/* Global values */
letter-spacing: inherit;
letter-spacing: initial;
letter-spacing: revert;
letter-spacing: revert-layer;
letter-spacing: unset;
```

### Values

[`normal`](#normal)

:   The normal letter spacing for the current font. Unlike a value of
    `0`, this keyword allows the [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    to alter the space between characters in order to justify text.

[`<length>`](length.md)

:   Specifies extra inter-character space *in addition to* the default
    space between characters. Values may be negative, but there may be
    implementation-specific limits. User agents may not further increase
    or decrease the inter-character space in order to justify text.

Accessibility concerns
----------------------

A large positive or negative `letter-spacing` value will make the
word(s) the styling is applied to unreadable. For text styled with a
very large positive value, the letters will be so far apart that the
word(s) will appear like a series of individual, unconnected letters.
For text styled with a very large negative value, the letters will
overlap each other to the point where the word(s) may be unrecognizable.

Legible letter-spacing must be determined on a case-by-case basis, as
different font families have different character widths. There is no one
value that can ensure all font families automatically maintain their
legibility.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

Internationalization concerns
-----------------------------

Some written languages should not have any letter spacing applied. For
instance, languages that use the Arabic script expect connected letters
to remain visually connected, as in the following example. Applying
letter spacing will lead the text to look broken.

> شسيبتنمك

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   an optimum value consisting of either an absolute length or the keyword `normal`
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
letter-spacing = 
  normal    |
  <length>  
```

Examples
--------

### Setting letter spacing

#### HTML

[html]

```html
<p class="normal">letter spacing</p>
<p class="em-wide">letter spacing</p>
<p class="em-wider">letter spacing</p>
<p class="em-tight">letter spacing</p>
<p class="px-wide">letter spacing</p>
```

#### CSS

[css]

```css
.normal {
  letter-spacing: normal;
}
.em-wide {
  letter-spacing: 0.4em;
}
.em-wider {
  letter-spacing: 1em;
}
.em-tight {
  letter-spacing: -0.05em;
}
.px-wide {
  letter-spacing: 6px;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  letter-spacing-property]](https://drafts.csswg.org/css-text/#letter-spacing-property)

  -----------------------------------------------------------------------------------------------

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

`letter-spacing`

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

`svg`

1

12

72

9

7

5.1

≤37

18

No

10.1

5

1.0

See also
--------

- [`font-kerning`](font-kerning.md)
- [`word-spacing`](word-spacing.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/letter-spacing>

word-spacing
============

The `word-spacing`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the length of space between words and between tags.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
word-spacing: normal;

/* <length> values */
word-spacing: 3px;
word-spacing: 0.3em;

/* Global values */
word-spacing: inherit;
word-spacing: initial;
word-spacing: revert;
word-spacing: revert-layer;
word-spacing: unset;
```

### Values

[`normal`](#normal)

:   The normal inter-word spacing, as defined by the current font and/or
    the browser.

[`<length>`](length.md)

:   Specifies extra spacing in addition to the intrinsic inter-word
    spacing defined by the font.

Examples
--------

### HTML

[html]

```html
<div id="mozdiv1">Lorem ipsum dolor sit amet.</div>
<div id="mozdiv2">Lorem ipsum dolor sit amet.</div>
```

### CSS

[css]

```css
#mozdiv1 {
  word-spacing: 15px;
}

#mozdiv2 {
  word-spacing: 5em;
}
```

Accessibility concerns
----------------------

A large positive or negative `word-spacing` value will make the
sentences the styling is applied to unreadable. For text styled with a
very large positive value, the words will be so far apart that it will
no longer appear to be a sentence. For text styled with a large negative
value, the words will overlap each other to the point where the
beginning and end of each word is unrecognizable.

Legible `word-spacing` must be determined on a case-by-case basis, as
different font families have different character widths. There is no one
value that can ensure all font families automatically maintain their
legibility.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  Percentages                        refer to the width of the affected glyph
  [Computed value](computed_value.md)   absolute [`<length>`](length.md)
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
word-spacing = 
  normal    |
  <length>  
```

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  word-spacing-property]](https://drafts.csswg.org/css-text/#word-spacing-property)

  -------------------------------------------------------------------------------------------

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

`word-spacing`

1

12

1

6

3.5

1

4.4

18

4

14

1

1.0

`percentages`

No

No

45

No

No

7

No

No

45

No

7

No

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

14

5

1.0

See also
--------

- [`letter-spacing`](letter-spacing.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/word-spacing>

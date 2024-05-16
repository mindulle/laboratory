hanging-punctuation
===================

The `hanging-punctuation`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies whether a punctuation mark should hang at the start or end of
a line of text. Hanging punctuation may be placed outside the line box.

Syntax
------

[css]

```css
/* Keyword values */
hanging-punctuation: none;
hanging-punctuation: first;
hanging-punctuation: last;
hanging-punctuation: force-end;
hanging-punctuation: allow-end;

/* Two keywords */
hanging-punctuation: first force-end;
hanging-punctuation: first allow-end;
hanging-punctuation: first last;
hanging-punctuation: last force-end;
hanging-punctuation: last allow-end;

/* Three keywords */
hanging-punctuation: first force-end last;
hanging-punctuation: first allow-end last;

/* Global values */
hanging-punctuation: inherit;
hanging-punctuation: initial;
hanging-punctuation: revert;
hanging-punctuation: revert-layer;
hanging-punctuation: unset;
```

The `hanging-punctuation` property may be specified with one, two, or
three space-separated values.

- **One-value** syntax uses any one of the keyword values in the list
    below.
- **Two-value** syntax uses one of the following:
  - `first` together with any one of `last`, `allow-end`, or
        `force-end`
  - `last` together with any one of `first`, `allow-end`, or
        `force-end`
- **Three-value** syntax uses one of the following:
  - `first`, `allow-end`, and `last`
  - `first`, `force-end`, and `last`

### Values

[`none`](#none)

:   No character hangs.

[`first`](#first)

:   An opening bracket or quote at the start of the first formatted line
    of an element hangs. This applies to:

    -   all characters in the Unicode categories
        [Ps](https://unicodeplus.com/category/Ps),
        [Pf](https://unicodeplus.com/category/Pf),
        [Pi](https://unicodeplus.com/category/Pi)
    -   the quote marks `U+0027` APOSTROPHE (`'`) and `U+0022` QUOTATION
        MARK (`"`).

[`last`](#last)

:   A closing bracket or quote at the end of the last formatted line of
    an element hangs. This applies to:

    -   all characters in the Unicode categories
        [Pe](https://unicodeplus.com/category/Pe),
        [Pf](https://unicodeplus.com/category/Pf),
        [Pi](https://unicodeplus.com/category/Pi)
    -   the quote marks `U+0027` APOSTROPHE (`'`) and `U+0022` QUOTATION
        MARK (`"`).

[`force-end`](#force-end)

:   A stop or comma at the end of a line hangs.

[`allow-end`](#allow-end)

:   A stop or comma at the end of a line hangs if it does not otherwise
    fit prior to justification.

Stops and commas that are allowed to hang include:

- `U+002C`, COMMA
- `U+002E`, FULL STOP
- `U+060C`, ARABIC COMMA
- `U+06D4`, ARABIC FULL STOP
- `U+3001`, IDEOGRAPHIC COMMA
- `U+3002`, IDEOGRAPHIC FULL STOP
- `U+FF0C`, FULLWIDTH COMMA
- `U+FF0E`, FULLWIDTH FULL STOP
- `U+FE50`, SMALL COMMA
- `U+FE51`, SMALL IDEOGRAPHIC COMMA
- `U+FE52`, SMALL FULL STOP
- `U+FF61`, HALFWIDTH IDEOGRAPHIC FULL STOP
- `U+FF64`, HALFWIDTH IDEOGRAPHIC COMMA

User agents may include additional characters.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
hanging-punctuation = 
  none                                            |
  [ first || [ force-end | allow-end ] || last ]  
```

Examples
--------

### Setting opening and closing quotes to hang

#### HTML

[html]

```html
<p>
  «For a moment, nothing happened. Then, after a second or so, nothing continued
  to happen.»
</p>

<p class="hanging">
  «For a moment, nothing happened. Then, after a second or so, nothing continued
  to happen.»
</p>

<p class="hanging right">
  «For a moment, nothing happened. Then, after a second or so, nothing continued
  to happen.»
</p>
```

#### CSS

[css]

```css
p {
  width: 15em;
  border: 1px solid #cccccc;
  font-size: 2rem;
  font-style: italic;
  margin: 1em;
}

p.hanging {
  hanging-punctuation: first last;
}

p.right {
  text-align: right;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  hanging-punctuation-property]](https://drafts.csswg.org/css-text/#hanging-punctuation-property)

  ---------------------------------------------------------------------------------------------------------

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

`hanging-punctuation`

No

No

No

No

No

10\[\"The `force-end` keyword is recognized but has no effect.\", \"The
characters `U+0027` and `U+0022` are not supported by the `first` and
`last` keywords.\"\]

No

No

No

No

10\[\"The `force-end` keyword is recognized but has no effect.\", \"The
characters `U+0027` and `U+0022` are not supported by the `first` and
`last` keywords.\"\]

No

See also
--------

- [`text-indent`](text-indent.md)
- [CSS Tricks: Hanging
    punctuation](https://css-tricks.com/almanac/properties/h/hanging-punctuation/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/hanging-punctuation>

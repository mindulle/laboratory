text-justify
============

The `text-justify` CSS property sets what type of justification should
be applied to text when [`text-align`](text-align.md)`: justify;` is set on
an element.

Syntax
------

[css]

```css
text-justify: none;
text-justify: auto;
text-justify: inter-word;
text-justify: inter-character;
text-justify: distribute; /* Deprecated value */

/* Global values */
text-justify: inherit;
text-justify: initial;
text-justify: revert;
text-justify: revert-layer;
text-justify: unset;
```

### Values

[`none`](#none)

:   The text justification is turned off. This has the same effect as
    not setting [`text-align`](text-align.md) at all, although it is useful
    if you need to turn justification on and off for some reason.

[`auto`](#auto)

:   The browser chooses the best type of justification for the current
    situation based on a balance between performance and quality, but
    also on what is most appropriate for the language of the text (e.g.,
    English, CJK languages, etc.). This is the default justification
    used if `text-justify` is not set at all.

[`inter-word`](#inter-word)

:   The text is justified by adding space between words (effectively
    varying [`word-spacing`](word-spacing.md)), which is most appropriate
    for languages that separate words using spaces, like English or
    Korean.

[`inter-character`](#inter-character)

:   The text is justified by adding space between characters
    (effectively varying [`letter-spacing`](letter-spacing.md)), which is
    most appropriate for languages like Japanese.

[`distribute`](#distribute) [Deprecated]

:   Exhibits the same behavior as `inter-character`; this value is kept
    for backwards compatibility.

Formal definition
-----------------

  ---------------------------------- --------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         inline-level and table-cell elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------------------------------

Formal syntax
-------------

```
text-justify = 
  auto             |
  none             |
  inter-word       |
  inter-character  
```

Examples
--------

### Demonstration of the different values of text-justify

[css]

```css
p {
  font-size: 1.5em;
  border: 1px solid black;
  padding: 10px;
  width: 95%;
  margin: 10px auto;
  text-align: justify;
}

.none {
  text-justify: none;
}

.auto {
  text-justify: auto;
}

.dist {
  text-justify: distribute;
}

.word {
  text-justify: inter-word;
}

.char {
  text-justify: inter-character;
}
```

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  text-justify-property]](https://drafts.csswg.org/css-text/#text-justify-property)

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

`text-justify`

32`inter-word` and `distribute` (deprecated) values are supported, but
`distribute` behavior is buggy.

79`inter-word` and `distribute` (deprecated) values are supported, but
`distribute` behavior is buggy.

12--79Standard values `inter-character` and `none` are supported. The
deprecated `distribute` value is also supported.

55

11Standard values `inter-character` and `none` are supported. The
deprecated `distribute` value is also supported.

19`inter-word` and `distribute` (deprecated) values are supported, but
`distribute` behavior is buggy.

No

No

32`inter-word` and `distribute` (deprecated) values are supported, but
`distribute` behavior is buggy.

55

No

No

No

See also
--------

- [`text-align`](text-align.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-justify>

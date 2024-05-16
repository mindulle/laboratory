initial-letter
==============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `initial-letter` CSS property sets styling for dropped, raised, and
sunken initial letters.

Syntax
------

[css]

```css
/* Keyword values */
initial-letter: normal;

/* Numeric values */
initial-letter: 1.5; /* Initial letter occupies 1.5 lines */
initial-letter: 3; /* Initial letter occupies 3 lines */
initial-letter: 3 2; /* Initial letter occupies 3 lines and
                           sinks 2 lines */

/* Global values */
initial-letter: inherit;
initial-letter: initial;
initial-letter: revert;
initial-letter: revert-layer;
initial-letter: unset;
```

The keyword value `normal`, or a `<number>` optionally followed by an
`<integer>`.

### Values

[`normal`](#normal)

:   No special initial-letter effect. Text behaves as normal.

[`<number>`](#number)

:   Defines the size of the initial letter, in terms of how many lines
    it occupies. Negative values are not allowed.

[`<integer>`](#integer)

:   Defines the number of lines the initial letter should sink when the
    size of it is given. Values must be greater than zero. If omitted,
    it duplicates the size value, floored to the nearest positive whole
    number.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         [`::first-letter`](::first-letter) pseudo-elements and inline-level first child of a block container
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     by computed value type
  ---------------------------------- ------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
initial-letter = 
  normal                               |
  <number [1,∞]> <integer [1,∞]>       |
  <number [1,∞]> && [ drop | raise ]?  
```

Examples
--------

### Setting initial letter size

#### HTML

[html]

```html
<p class="normal">Initial letter is normal</p>
<p class="onefive">Initial letter occupies 1.5 lines</p>
<p class="three">Initial letter occupies 3 lines</p>
```

#### CSS

[css]

```css
.normal::first-letter {
  -webkit-initial-letter: normal;
  initial-letter: normal;
}

.onefive::first-letter {
  -webkit-initial-letter: 1.5;
  initial-letter: 1.5;
}

.three::first-letter {
  -webkit-initial-letter: 3;
  initial-letter: 3;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Inline Layout Module Level 3\
  [\#
  sizing-drop-initials]](https://drafts.csswg.org/css-inline/#sizing-drop-initials)

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

`initial-letter`

110

110

No

No

96

9See [bug 229090](https://webkit.org/b/229090) for the unprefixed
property.

110

110

No

74

9See [bug 229090](https://webkit.org/b/229090) for the unprefixed
property.

21.0

See also
--------

- [`initial-letter-align`](initial-letter-align.md)
- [Drop caps in
    CSS](https://www.oddbird.net/2017/01/03/initial-letter/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/initial-letter>

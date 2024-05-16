white-space
===========

The `white-space` CSS property sets how [white
space](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace)
inside an element is handled.

Try it
------

The property specifies two things:

- Whether and how white space is
    [collapsed](#collapsing_of_white_space).
- Whether and how lines wrap.

**Note:** To make words break *within themselves*, use
[`overflow-wrap`](overflow-wrap.md), [`word-break`](word-break.md), or
[`hyphens`](hyphens.md) instead.

Syntax
------

[css]

```css
/* Single keyword values */
white-space: normal;
white-space: nowrap;
white-space: pre;
white-space: pre-wrap;
white-space: pre-line;
white-space: break-spaces;

/* white-space-collapse and text-wrap shorthand values */
white-space: collapse balance;
white-space: preserve nowrap;

/* Global values */
white-space: inherit;
white-space: initial;
white-space: revert;
white-space: revert-layer;
white-space: unset;
```

### Values

`white-space` property values can be specified as a single keyword
chosen from the list of values below, or two values representing
shorthand for the [`white-space-collapse`](white-space-collapse.md) and
[`text-wrap`](text-wrap.md) properties.

[`normal`](#normal)

:   Sequences of white space are
    [collapsed](#collapsing_of_white_space). Newline characters in the
    source are handled the same as other white space. Lines are broken
    as necessary to fill line boxes.

[`nowrap`](#nowrap)

:   [Collapses](#collapsing_of_white_space) white space as for `normal`,
    but suppresses line breaks (text wrapping) within the source.

[`pre`](#pre)

:   Sequences of white space are preserved. Lines are only broken at
    newline characters in the source and at
    [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br)
    elements.

[`pre-wrap`](#pre-wrap)

:   Sequences of white space are preserved. Lines are broken at newline
    characters, at
    [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br),
    and as necessary to fill line boxes.

[`pre-line`](#pre-line)

:   Sequences of white space are
    [collapsed](#collapsing_of_white_space). Lines are broken at newline
    characters, at
    [`<br>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br),
    and as necessary to fill line boxes.

[`break-spaces`](#break-spaces)

:   The behavior is identical to that of `pre-wrap`, except that:

    -   Any sequence of preserved white space always takes up space,
        including at the end of the line.
    -   A line-breaking opportunity exists after every preserved white
        space character, including between white space characters.
    -   Such preserved spaces take up space and do not hang, thus
        affecting the box\'s intrinsic sizes (`min-content` size and
        `max-content` size).

The following table summarizes the behavior of the various `white-space`
keyword values:

                   New lines   Spaces and tabs   Text wrapping   End-of-line spaces   End-of-line other space separators
  ---------------- ----------- ----------------- --------------- -------------------- ------------------------------------
  `normal`         Collapse    Collapse          Wrap            Remove               Hang
  `nowrap`         Collapse    Collapse          No wrap         Remove               Hang
  `pre`            Preserve    Preserve          No wrap         Preserve             No wrap
  `pre-wrap`       Preserve    Preserve          Wrap            Hang                 Hang
  `pre-line`       Preserve    Collapse          Wrap            Remove               Hang
  `break-spaces`   Preserve    Preserve          Wrap            Wrap                 Wrap

**Note:** There is a distinction made between **spaces** and **other
space separators**. These are defined as follows:

[spaces](#spaces)

:   Spaces (U+0020), tabs (U+0009), and segment breaks (such as
    newlines).

[other space separators](#other_space_separators)

:   All other space separators defined in Unicode, other than those
    already defined as spaces.

Where white space is said to *hang*, this can affect the size of the box
when measured for intrinsic sizing.

Collapsing of white space
-------------------------

The [`white-space-collapse`](white-space-collapse.md) property page
explains the [](white-space-collapse.md#collapsing_of_white_space).

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
white-space = 
  normal        |
  pre           |
  nowrap        |
  pre-wrap      |
  break-spaces  |
  pre-line      
```

Examples
--------

### Basic example

[css]

```css
code {
  white-space: pre;
}
```

### Line breaks inside \<pre\> elements

[css]

```css
pre {
  white-space: pre-wrap;
}
```

### In action

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Text Module Level 3\
  [\#
  white-space-property]](https://drafts.csswg.org/css-text/#white-space-property)

  -----------------------------------------------------------------------------------------

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

`white-space`

1

12

1

5.5

4

1

4.4

18

4

10.1

1

1.0

`break-spaces`

76

79

69

No

62

13.1

76

76

79

54

13.4

12.0

`nowrap`

1

12

1

5.5

4

1

4.4

18

4

10.1

1

1.0

`pre`

1

12

1

6

4

1

37

18

4

14

1

1.0

`pre-line`

1

12

3.5

8

9.5

3

37

18

4

14

1

1.0

`pre-wrap`

1

12

31--3.6

8From Internet Explorer 5.5 to 7, `word-wrap: break-word;` can be used
for line breaks in `pre` elements.

8

3

37

18

4

14

1

1.0

`shorthand_values`

114Accepts shorthand values for `white-space-collapse` and `text-wrap`
only.

114Accepts shorthand values for `white-space-collapse` and `text-wrap`
only.

No

No

100Accepts shorthand values for `white-space-collapse` and `text-wrap`
only.

No

114Accepts shorthand values for `white-space-collapse` and `text-wrap`
only.

114Accepts shorthand values for `white-space-collapse` and `text-wrap`
only.

No

NoAccepts shorthand values for `white-space-collapse` and `text-wrap`
only.

No

NoAccepts shorthand values for `white-space-collapse` and `text-wrap`
only.

`svg_support`

No

12--79

36

10

No

No

No

No

36

No

No

No

`textarea_support`

1

12

36

5.5

4

1

37

18

36

14

1

1.0

See also
--------

- Properties that define how words break *within themselves*:
    [`overflow-wrap`](overflow-wrap.md), [`word-break`](word-break.md),
    [`hyphens`](hyphens.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/white-space>

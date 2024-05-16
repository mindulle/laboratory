text-align
==========

The `text-align` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the horizontal alignment of the inline-level content
inside a block element or table-cell box. This means it works like
[`vertical-align`](vertical-align.md) but in the horizontal direction.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
text-align: start;
text-align: end;
text-align: left;
text-align: right;
text-align: center;
text-align: justify;
text-align: justify-all;
text-align: match-parent;

/* Character-based alignment in a table column */
text-align: ".";
text-align: "." center;

/* Block alignment values (Non-standard syntax) */
text-align: -moz-center;
text-align: -webkit-center;

/* Global values */
text-align: inherit;
text-align: initial;
text-align: revert;
text-align: revert-layer;
text-align: unset;
```

The `text-align` property is specified in one of the following ways:

- Using the keyword values `start`, `end`, `left`, `right`, `center`,
    `justify`, `justify-all`, or `match-parent`.
- Using a `<string>` value only, in which case the other value
    defaults to `right`.
- Using both a keyword value and a [`<string>`](#string) value.

### Values

[`start`](#start)

:   The same as `left` if direction is left-to-right and `right` if
    direction is right-to-left.

[`end`](#end)

:   The same as `right` if direction is left-to-right and `left` if
    direction is right-to-left.

[`left`](#left)

:   The inline contents are aligned to the left edge of the line box.

[`right`](#right)

:   The inline contents are aligned to the right edge of the line box.

[`center`](#center)

:   The inline contents are centered within the line box.

[`justify`](#justify)

:   The inline contents are justified. Text should be spaced to line up
    its left and right edges to the left and right edges of the line
    box, except for the last line.

[`justify-all`](#justify-all) [Experimental]

:   Same as `justify`, but also forces the last line to be justified.

[`match-parent`](#match-parent)

:   Similar to `inherit`, but the values `start` and `end` are
    calculated according to the parent\'s [`direction`](direction.md) and
    are replaced by the appropriate `left` or `right` value.

[`<string>`](string.md) [Experimental]

:   When applied to a table cell, specifies the alignment character
    around which the cell\'s contents will align.

Accessibility concerns
----------------------

The inconsistent spacing between words created by justified text can be
problematic for people with cognitive concerns such as Dyslexia.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 \| Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `start`, or a nameless value that acts as `left` if [`direction`](direction.md) is `ltr`, `right` if [`direction`](direction.md) is `rtl` if `start` is not supported by the browser.
  Applies to                         block containers
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified, except for the `match-parent` value which is calculated against its parent\'s `direction` value and results in a computed value of either `left` or `right`
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
text-align = 
  start         |
  end           |
  left          |
  right         |
  center        |
  justify       |
  match-parent  |
  justify-all   
```

Examples
--------

### Start alignment

#### HTML

[html]

```html
<p class="example">
  Integer elementum massa at nulla placerat varius. Suspendisse in libero risus,
  in interdum massa. Vestibulum ac leo vitae metus faucibus gravida ac in neque.
  Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>
```

#### CSS

[css]

```css
.example {
  text-align: start;
  border: solid;
}
```

#### Result

### Centered text

#### HTML

[html]

```html
<p class="example">
  Integer elementum massa at nulla placerat varius. Suspendisse in libero risus,
  in interdum massa. Vestibulum ac leo vitae metus faucibus gravida ac in neque.
  Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>
```

#### CSS

[css]

```css
.example {
  text-align: center;
  border: solid;
}
```

#### Result

### Example using \"justify\"

#### HTML

[html]

```html
<p class="example">
  Integer elementum massa at nulla placerat varius. Suspendisse in libero risus,
  in interdum massa. Vestibulum ac leo vitae metus faucibus gravida ac in neque.
  Nullam est eros, suscipit sed dictum quis, accumsan a ligula.
</p>
```

#### CSS

[css]

```css
.example {
  text-align: justify;
  border: solid;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\# text-align]](https://drafts.csswg.org/css-logical/#text-align)

[CSS Text Module Level 3\
  [\#
  text-align-property]](https://drafts.csswg.org/css-text/#text-align-property)
  ---------------------------------------------------------------------------------------

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

`text-align`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`block_alignment_values`

11

7979

11

No

1515

≤41.31

37

1818

44

1414

≤3.211

1.01.0

`flow_relative_values_start_and_end`

1

79

1

No

15

3.1

37

18

4

14

2

1.0

`match-parent`

16

79

40

No

15

15.4

37

18

40

14

15.4

1.0

See also
--------

- [`margin: auto`](margin.md), [`margin-left: auto`](margin-left.md),
    [`vertical-align`](vertical-align.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-align>

Pseudo-elements
===============

A CSS **pseudo-element** is a keyword added to a selector that lets you
style a specific part of the selected element(s).

Syntax
------

[css]

```css
selector::pseudo-element {
  property: value;
}
```

For example, [`::first-line`](::first-line) can be used to change the
font of the first line of a paragraph.

[css]

```css
/* The first line of every <p> element. */
p::first-line {
  color: blue;
  text-transform: uppercase;
}
```

Double colons (`::`) are used for pseudo-elements. This distinguishes
pseudo-elements from [pseudo-classes](pseudo-classes.md) that use single
colon (`:`) in their notation.

You can use only one pseudo-element in a selector. The pseudo-element
must appear after all the other components in the
[complex](selector_structure.md#complex_selector) or
[compound](selector_structure.md#compound_selector) selector
in which it appears. For example, you can select a paragraph\'s first
line using `p::first-line` but not the first-line\'s children or a
hovered first line. So both `p::first-line > *` and
`p::first-line:hover` are invalid.

While it is not possible to select an element based on its *state* by
using pseudo-elements, a pseudo-element can be used to select and style
a part of an element that already has a state applied to it. For
example, `p:hover::first-line` selects the first line (pseudo-element)
of a paragraph when the paragraph itself is being hovered
(pseudo-class).

**Note:** When a [](selector_structure.md#selector_list) contains an
invalid selector, the entire style block is ignored.

List of pseudo-elements
-----------------------

Pseudo-elements defined by a set of CSS specifications include the
following:

A

- [`::after`](::after)

B

- [`::backdrop`](::backdrop)
- [`::before`](::before)

C

- [`::cue`](::cue)
- [`::cue-region`](::cue-region)

F

- [`::first-letter`](::first-letter)
- [`::first-line`](::first-line)
- [`::file-selector-button`](::file-selector-button)

G

- [`::grammar-error`](::grammar-error)
    [Experimental]

M

- [`::marker`](::marker)

P

- [`::part()`](::part)
- [`::placeholder`](::placeholder)

S

- [`::selection`](::selection)
- [`::slotted()`](::slotted)
- [`::spelling-error`](::spelling-error)
    [Experimental]

T

- [`::target-text`](::target-text) [Experimental]

**Note:** Browsers support the single colon syntax only for the original
four pseudo-elements: `::before`, `::after`, `::first-line`, and
`::first-letter`.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  ](https://drafts.csswg.org/css-pseudo/)

  [CSS Positioned Layout Module Level 4\
  ](https://drafts.csswg.org/css-position-4/)

  [CSS Shadow Parts\
  ](https://drafts.csswg.org/css-shadow-parts/)

[WebVTT: The Web Video Text Tracks Format\
  ](https://w3c.github.io/webvtt/)
  -----------------------------------------------------------------------

See also
--------

- [CSS pseudo-element](css_pseudo-elements.md) module
- [Pseudo-classes](pseudo-classes.md)
- [CSS selectors](css_selectors.md) module
- [CSS building blocks: Pseudo-classes and
    pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements>

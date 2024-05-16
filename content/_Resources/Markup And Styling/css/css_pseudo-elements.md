CSS pseudo-elements
===================

The **CSS pseudo-element** module defines abstract elements that are not
directly present in the document tree. These abstract elements, called
pseudo-elements, represent portions of the render tree that can be
selected and styled. Pseudo-elements are used to create abstractions
about the document tree beyond those provided by the document tree.

Pseudo-elements are prefixed with a double colon (`::`). You add
pseudo-elements to selectors (as in `p::first-line`) to target and style
these faux elements.

Pseudo-elements enable targeting entities not included in HTML and
sections of content that cannot be targeted otherwise without adding
extra markup. Consider the placeholder of an
[`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
element. This is an abstract element and not a distinct node in the
document tree. You can select this placeholder by using the
[`::placeholder`](::placeholder) pseudo-element. As another example, the
[`::selection`](::selection) pseudo-element matches the content
currently highlighted by a user, allowing you to style what is matched
as the user interacts with the content and changes the selection.
Similarly, the [`::first-line`](::first-line) pseudo-element targets the
first line of an element, updating automatically if the character count
of the first line changes, without having to query the element\'s line
length.

Reference
---------

### Selectors

- [`::after`](::after)
- [`::before`](::before)
- [`::file-selector-button`](::file-selector-button)
- [`::first-letter`](::first-letter)
- [`::first-line`](::first-line)
- [`::grammar-error`](::grammar-error)
- [`::marker`](::marker)
- [`::placeholder`](::placeholder)
- [`::selection`](::selection)
- [`::spelling-error`](::spelling-error)
- [`::target-text`](::target-text)

### Interfaces

- [`CSSPseudoElement`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement)
    interface
  - [`CSSPseudoElement.element`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement/element)
        property
  - [`CSSPseudoElement.type`](https://developer.mozilla.org/en-US/docs/Web/API/CSSPseudoElement/type)
        property

### Terms

- [Pseudo-element](https://developer.mozilla.org/en-US/docs/Glossary/Pseudo-element)
    glossary term

Guides
------

[CSS pseudo-elements](pseudo-elements.md)

:   Alphabetical list of pseudo-elements defined by all the CSS
    specifications and WebVTT.

[Building blocks: Pseudo-classes and pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements)

:   Part of CSS building blocks section on selectors. This article
    defines what a pseudo-element is and how it can be combined with
    pseudo-classes and be used for generating content with `::before`
    and `::after` pseudo-elements.

[How to create fancy boxes using pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Howto/Create_fancy_boxes#pseudo-elements)

:   Example of styling generated content using `::before` and `::after`
    pseudo-elements for visual effects.

Related concepts
----------------

- [`::backdrop`](::backdrop)
- Web Video Text Tracks Format (WebVTT) cues:
  - [`::cue`](::cue)
  - [`::cue()`](::cue)
  - [`::cue-region`](::cue-region)
- [CSS scoping](css_scoping.md) module
  - [`:host`](:host)
  - [`:host()`](:host_function)
  - [`:host-context()`](:host-context)
  - [`::slotted()`](::slotted)
- [CSS shadow parts](css_shadow_parts.md) module
  - [`::part`](::part)
- [CSS selectors](css_selectors.md)
  - [Attribute selectors](attribute_selectors.md)
  - [Combinators](selectors_and_combinators.md#combinators)
  - [Class selectors](class_selectors.md)
  - [ID selectors](id_selectors.md)
  - [Type selectors](type_selectors.md)
  - [Pseudo-classes](pseudo-classes.md)
  - [Universal selectors](universal_selectors.md)
- [`placeholder`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#placeholder)
    attribute of the `<input>` element
- [`:placeholder-shown`](:placeholder-shown) selector
- [CSS generated content](css_generated_content.md)
  - [`content`](content.md) property
  - [`quotes`](quotes.md) property
- [Text
    fragments](https://developer.mozilla.org/en-US/docs/Web/Text_fragments)
- [`AnimationEvent.pseudoElement`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/pseudoElement)
    property
- [`KeyframeEffect.pseudoElement`](https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffect/pseudoElement)
    property
- [`TransitionEvent.pseudoElement`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent/pseudoElement)
    property

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Pseudo-Elements Module Level 4\
  ](https://drafts.csswg.org/css-pseudo/)

  -----------------------------------------------------------------------

See also
--------

- [Specificity](specificity.md)
- [CSS selectors](css_selectors.md) module
- [CSS shadow-parts](css_shadow_parts.md) module
- [CSS generated content](css_generated_content.md) module
- [CSS positioned layout](css_positioned_layout.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_pseudo-elements>

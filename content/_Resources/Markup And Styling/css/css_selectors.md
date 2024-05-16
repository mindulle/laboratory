CSS selectors
=============

The **CSS selectors** module defines the patterns to select elements to
which a set of CSS rules are then applied along with their
[`specificity`](specificity.md). The CSS selectors module provides us with
more than 60 selectors and five combinators. [Other
modules](#related_concepts) provide additional pseudo-class selectors
and pseudo-elements.

In CSS, selectors are patterns used to match, or select, the elements
you want to style. Selectors are also used in JavaScript to enable
selecting the DOM nodes to return as a
[`NodeList`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList).

Selectors, whether used in CSS or JavaScript, enable targeting HTML
elements based on their type, attributes, current states, and even
position in the DOM. Combinators allow you to be more precise when
selecting elements by enabling selecting elements based on their
relationship to other elements.

Reference
---------

### Combinators and separators

- `+` ([Next-sibling combinator](next-sibling_combinator.md))
- `>` ([Child combinator](child_combinator.md))
- `||` ([Column combinator](column_combinator.md))
    [Experimental]
- `~` ([Subsequent sibling combinator](subsequent-sibling_combinator.md))
- \" \" ([Descendant combinator](descendant_combinator.md))
- `|` ([Namespace separator](namespace_separator.md))

### Selectors

- [`:active`](:active)
- [`:any-link`](:any-link)
- [`:autofill`](:autofill)
- [`:blank`](:blank)
- [`:buffering`](:buffering)
- [`:checked`](:checked)
- [`:current`](:current)
- [`:current()`](:current)
- [`:default`](:default)
- [`:defined`](:defined)
- [`:dir()`](:dir)
- [`:disabled`](:disabled)
- [`:empty`](:empty)
- [`:enabled`](:enabled)
- [`:first-child`](:first-child)
- [`:first-of-type`](:first-of-type)
- [`:focus`](:focus)
- [`:focus-visible`](:focus-visible)
- [`:focus-within`](:focus-within)
- [`:fullscreen`](:fullscreen)
- [`:future`](:future)
- [`:has()`](:has)
- [`:hover`](:hover)
- [`:indeterminate`](:indeterminate)
- [`:in-range`](:in-range)
- [`:invalid`](:invalid)
- [`:is()`](:is)
- [`:lang()`](:lang)
- [`:last-child`](:last-child)
- [`:last-of-type`](:last-of-type)
- [`:link`](:link)
- [`:local-link`](:local-link)
- `:matches()` (obsolete legacy selector alias for [`:is()`](:is))
- [`:modal`](:modal)
- [`:muted`](:muted)
- [`:not()`](:not)
- [`:nth-child()`](:nth-child)
- [`:nth-of-type()`](:nth-of-type)
- [`:nth-last-child()`](:nth-last-child)
- [`:nth-last-of-type()`](:nth-last-of-type)
- [`:nth-of-type()`](:nth-of-type)
- [`:only-child`](:only-child)
- [`:only-of-type`](:only-of-type)
- [`:optional`](:optional)
- [`:out-of-range`](:out-of-range)
- [`:past`](:past)
- [`:paused`](:paused)
- [`:picture-in-picture`](:picture-in-picture)
- [`:placeholder-shown`](:placeholder-shown)
- [`:playing`](:playing)
- [`:read-only`](:read-only)
- [`:read-write`](:read-write)
- [`:required`](:required)
- [`:root`](:root)
- [`:scope`](:scope)
- [`:seeking`](:seeking)
- [`:stalled`](:stalled)
- [`:target`](:target)
- [`:target-within`](:target-within)
- [`:user-invalid`](:user-invalid)
- [`:user-valid`](:user-valid)
- [`:valid`](:valid)
- [`:visited`](:visited)
- [`:volume-locked`](:volume-locked)
- [`:where()`](:where)
- [`:-webkit-`
    pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/WebKit_Extensions#pseudo-classes)
- [Attribute selectors](attribute_selectors.md)
- [Class selector](class_selectors.md)
- [ID selectors](id_selectors.md)
- [Type selectors](type_selectors.md)
- [Universal selectors](universal_selectors.md)

Terms
-----

- [Pseudo-class](https://developer.mozilla.org/en-US/docs/Glossary/Pseudo-class)
    glossary term
- [](pseudo-classes.md#functional_pseudo-classes)
- [Combinators](selectors_and_combinators.md#combinators)
- [](selectors_and_combinators.md#simple-selector)
- [](selectors_and_combinators.md#compound-selector)
- [](selectors_and_combinators.md#complex-selector)
- [](selectors_and_combinators.md#relative-selector)
- [Selector list](selector_list.md)
- [Specificity](specificity.md)

Guides
------

[CSS selectors and combinators](selectors_and_combinators.md)

:   Overview of the different types of simple selectors and various
    combinators defined in the CSS selectors and the CSS pseudo modules.

[CSS selector structure](selector_structure.md)

:   Explanation of the structure of CSS selectors and the terminologies
    introduced in the CSS selectors module, ranging from \"simple
    selector\" to \"forgiving relative selector list\".

[Pseudo classes](pseudo-classes.md)

:   Lists the pseudo-classes, selectors that allow the selection of
    elements based on state information that is not contained in the
    document tree, defined in the various CSS modules and HTML.

[Learn: CSS selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

:   Part of CSS building blocks, includes tutorials on [Type, class, and
    ID
    selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Type_Class_and_ID_Selectors),
    [Attribute
    selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Attribute_selectors),
    [Pseudo-classes and
    pseudo-elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Pseudo-classes_and_pseudo-elements),
    [Combinators](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors/Combinators),
    [Cascade, specificity, and
    inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance),
    and [Cascade
    layers](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_layers).

[Using the `:target` pseudo-class in selectors](css_selectors/using_the_:target_pseudo-class_in_selectors)

:   Learn how to use the [`:target`](:target) pseudo-class to style the
    target element a URL\'s fragment identifier.

[Learn: UI pseudo-classes](https://developer.mozilla.org/en-US/docs/Learn/Forms/UI_pseudo-classes)

:   Learn the different UI pseudo-classes available for styling forms in
    different states.

[Locating DOM elements using selectors](https://developer.mozilla.org/en-US/docs/Web/API/Document_object_model/Locating_DOM_elements_using_selectors)

:   The selectors API enables using selectors in JavaScript to retrieve
    element nodes from the DOM.

Related concepts
----------------

- [`:popover-open`](:popover-open) pseudo-class
- [CSS nesting](css_nesting.md) module
  - : [`&` nesting selector](nesting_selector.md)
- [CSS scoping](css_scoping.md) module
  - [`:host`](:host) pseudo-class
  - [`:host()`](:host_function) pseudo-class
  - [`:host-context()`](:host-context) pseudo-class
  - [`::slotted`](::slotted) pseudo-element
- [CSS pseudo-element module](css_pseudo-elements.md) (representing
    entities not included in HTML)
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
- [CSS shadow parts module](css_shadow_parts.md)
  - [`::part`](::part) pseudo-element
- [CSS positioned layout module](css_positioned_layout.md)
  - [`::backdrop`](::backdrop)
- Other [pseudo-elements](pseudo-elements.md)
  - [`::cue`](::cue)
  - [`::cue-region`](::cue-region)
- [`@namespace`](@namespace.md) at-rule
- [`!important`](important.md)
- [Specificity](specificity.md)
- [Cascade](cascade.md)
- [`Document.querySelector`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector)
    method
- [`Document.querySelectorAll`](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelectorAll)
    method
- [`NodeList.forEach()`](https://developer.mozilla.org/en-US/docs/Web/API/NodeList/forEach)
    method

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Selectors Level 4\
  ](https://drafts.csswg.org/selectors/)

  -----------------------------------------------------------------------

See also
--------

- [CSS pseudo-element module](css_pseudo-elements.md)
- [CSS cascade and inheritance module](css_cascade.md)
- [CSS nesting module](css_nesting.md)
- [Using shadow
    DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_selectors>

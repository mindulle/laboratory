CSS scoping
===========

The **CSS scoping** module defines the CSS scoping and encapsulation
mechanisms, focusing on the [Shadow
DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)
[scoping](https://css.oddbird.net/scope/) mechanism.

CSS styles are either global in scope or scoped to a [shadow
tree](https://developer.mozilla.org/en-US/docs/Glossary/Shadow_tree).
Globally scoped styles apply to all the elements in the node tree that
match the selector, including custom elements in that tree, but not to
the shadow trees composing each custom element. Selectors and their
associated style definitions don\'t bleed between scopes.

Within the CSS of a shadow tree, selectors don\'t select elements
outside the tree, either in the global scope or in other shadow trees.
Each custom element has its own shadow tree, which contains all the
components that make up the custom element (but not the custom element,
or \"host\", itself).

Sometimes it\'s useful to be able to style a host from inside the shadow
tree context. The CSS scoping module makes this possible by defining
selectors that:

- Enable a shadow tree to style its host.
- Enable external CSS to style elements within a shadow DOM (but only
    if the associated custom element is set up to accept external
    styles).

Reference
---------

### Selectors

- [`:host`](:host)
- [`:host()`](:host_function)
- [`:host-context()`](:host-context)
- [`::slotted`](::slotted)

Guides
------

[Web components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)

:   An introduction to the different technologies used to create
    reusable web components --- custom elements whose functionality is
    encapsulated away from the rest of your code.

[Using shadow DOM](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_shadow_DOM)

:   Shadow DOM fundamentals, including attaching a shadow DOM to an
    element, adding to the shadow DOM tree, and styling.

[Using templates and slots](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_templates_and_slots)

:   Defining reusable HTML structure using
    [`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
    and
    [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot)
    elements, and using that structure inside web components.

[Using custom elements](https://developer.mozilla.org/en-US/docs/Web/API/Web_components/Using_custom_elements)

:   Introduction to the Custom Elements API, the JavaScript API used to
    create custom elements that encapsulate functionality.

Related concepts
----------------

- CSS [`:defined`](:defined) pseudo-class
- CSS [`::part`](::part) pseudo-element
- HTML
    [`<template>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/template)
    element
- HTML
    [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot)
    element
- HTML
    [`slot`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/slot)
    attribute
- [Shadow
    tree](https://developer.mozilla.org/en-US/docs/Glossary/Shadow_tree)
    glossary term
- [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM)
    glossary term
- [](selector_structure.md#compound_selector) term
- [Selector list](selector_list.md) term
- [Web
    components](https://developer.mozilla.org/en-US/docs/Web/API/Web_components)
    interfaces, properties, and methods
  - [`CustomElementRegistry`](https://developer.mozilla.org/en-US/docs/Web/API/CustomElementRegistry)
        interface
  - [`Element`](https://developer.mozilla.org/en-US/docs/Web/API/Element)
        API
    - [`Element.slot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/slot)
            property
    - [`Element.assignedSlot`](https://developer.mozilla.org/en-US/docs/Web/API/Element/assignedSlot)
            property
    - [`Element.attachShadow()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/attachShadow)
            method
  - [`HTMLSlotElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSlotElement)
        interface
  - [`HTMLTemplateElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLTemplateElement)
        interface
  - [`ShadowRoot`](https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot)
        interface

**Note:** Despite the name, the [`:scope`](:scope) pseudo-class, which
represents elements that are a reference point (or scope) for selectors
to match against, is defined in the [CSS
pseudo-classes](css_pseudo-classes) module. It is
otherwise unrelated to the CSS scoping module, which is focused on
scoping as it pertains to the Shadow DOM scoping mechanism.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Scoping Module Level 1\
  ](https://drafts.csswg.org/css-scoping/)

  -----------------------------------------------------------------------

See also
--------

- [CSS selectors](css_selectors.md) module
- [CSS pseudo elements](css_pseudo-elements.md) module
- [CSS namespaces](css_namespaces.md) module
- [CSS shadow-parts](css_shadow_parts.md) module
- [Template, slot, and shadow](https://web.dev/learn/html/template/)
    on web.dev (2023)
- [Custom element best
    practices](https://web.dev/custom-elements-best-practices/) on
    web.dev (2019)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_scoping>

CSS generated content
=====================

The **CSS generated content** module defines how an element\'s content
can be replaced and content can be added to a document with CSS.

Generated content can be used for content replacement, in which case the
content of a DOM node is replaced with a CSS `<image>`. The CSS
generated content also enables generating language-specific quotes,
creating custom list item numbers and bullets, and visually adding
content by generating content on select pseudo-elements as anonymous
replaced elements.

### Generated content in action

The HTML for this sample is a single, empty
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
inside an otherwise empty
[`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body).
The snowman was created with [CSS images](css_images.md) and [](css_backgrounds_and_borders.md). The carrot nose
was added using generated content: an empty box with a wide orange
[`left border`](border-left.md) added to the [`::before`](::before)
pseudo-element. The text is also generated content: \"only one \<div\>\"
was generated with the [`content`](content.md) property applied to the
[`::after`](::after) pseudo-element.

To see the code for this animation, [view the source on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/generated_content.html).

Reference
---------

### Properties

- [`content`](content.md)
- [`quotes`](quotes.md)

**Note:** The CSS generated content module introduces four at-risk
properties that have not been implemented: `string-set`,
`bookmark-label`, `bookmark-level`, and `bookmark-state`.

### Functions

The CSS generated content module introduces six yet-to-be implemented
CSS functions including `content()`, `string()`, and `leader()`, and the
three [`<target>`](content.md#target) functions `target-counter()`,
`target-counters()`, and `target-text()`.

### Data types

- [`<content-list>`](content.md#content-list)
- `<content-replacement>` (see [`<image>`](_Resources/Markup%20And%20Styling/css/image.md))
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md)
- [`<counter>`](content.md#counter)
- [`<quote>`](content.md#quote)
- [`<target>`](content.md#target)

Guides
------

[\"How to\" guide for generated content](https://developer.mozilla.org/en-US/docs/Learn/CSS/Howto/Generated_content)

:   Learn how to add text or image content to a document using the
    [`content`](content.md) property.

[Create fancy boxes with generated content](https://developer.mozilla.org/en-US/docs/Learn/CSS/Howto/Create_fancy_boxes)

:   Example of styling generated content for visual effects.

Related concepts
----------------

- [CSS pseudo-elements](css_pseudo-elements.md) module
  - [`::before`](::before) pseudo-element
  - [`::after`](::after) pseudo-element
  - [`::marker`](::marker) pseudo-element
- [CSS lists and counters](css_lists.md) module
  - [`counter()`](counter.md) function
  - [`counters()`](counters.md) function
  - [`counter-increment`](counter-increment.md) property
  - [`counter-reset`](counter-reset.md) property
- [CSS values and units](css_values_and_units.md) module
  - [`attr()`](attr.md) function
  - [`<string>`](string.md) data type
  - [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) data type

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Generated Content Module Level 3\
  ](https://drafts.csswg.org/css-content/)

  -----------------------------------------------------------------------

See also
--------

- [CSS pseudo-elements](css_pseudo-elements.md) module
- [CSS lists and counters](css_lists.md) module
- [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_generated_content>

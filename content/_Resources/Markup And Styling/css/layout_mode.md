Layout mode
===========

A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **layout
mode**, sometimes called *layout*, is an algorithm that determines the
position and size of boxes based on the way they interact with their
sibling and ancestor boxes. There are several of them:

- *[Normal flow](css_flow_layout.md)* --- all elements are part of normal
    flow until you do something to take them out of it. Normal flow
    includes *block layout*, designed for laying out boxes such as
    paragraphs and *inline layout*, which lays out inline items such as
    text.
- [*Table layout*](css_table.md), designed for laying out tables.
- *Float layout*, designed to cause an item to position itself left or
    right with the rest of the content in normal flow wrapping around
    it.
- [*Positioned layout*](css_positioned_layout.md), designed for
    positioning elements without much interaction with other elements.
- [*Multi-column layout*](css_multicol_layout.md), designed for laying
    content out in columns as in a newspaper.
- [*Flexible box layout*](css_flexible_box_layout.md), designed for
    laying out complex pages that can be resized smoothly.
- [*Grid layout*](css_grid_layout.md), designed for laying out elements
    relative to a fixed grid.

**Note:** Not all [CSS properties](index) apply to all *layout modes*.
Most of them apply to one or two of them and have no effect if they are
set on an element participating in another layout mode.

See also
--------

- CSS key concepts:
  - [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
  - [At-rules](at-rule.md)
  - [Comments](comments.md)
  - [Specificity](specificity.md)
  - [Inheritance](inheritance.md)
  - [Box model](introduction_to_the_css_box_model.md)
  - [Visual formatting models](visual_formatting_model.md)
  - [Margin collapsing](mastering_margin_collapsing.md)
  - Values
    - [Initial values](initial_value.md)
    - [Computed values](computed_value.md)
    - [Used values](used_value.md)
    - [Actual values](actual_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Layout_mode>

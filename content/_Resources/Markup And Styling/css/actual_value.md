Actual value
============

The **actual value** of a
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is the
[used value](used_value.md) of that property after any necessary
approximations have been applied. For example, a [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
that can only render borders with a whole-number pixel width may round
the thickness of the border to the nearest integer.

Calculating a property\'s actual value
--------------------------------------

The [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
performs four steps to calculate a property\'s actual (final) value:

1. First, the [specified value](specified_value.md) is determined based on
    the result of [cascading](cascade.md), [inheritance](inheritance.md), or
    using the [initial value](initial_value.md).
2. Next, the [computed value](computed_value.md) is calculated according
    to the specification (for example, a `span` with
    `position: absolute` will have its computed `display` changed to
    `block`).
3. Then, layout is calculated, resulting in the [](used_value.md).
4. Finally, the used value is transformed according to the limitations
    of the local environment, resulting in the actual value.

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  actual-value]](https://www.w3.org/TR/CSS22/cascade.html#actual-value)

  -------------------------------------------------------------------------------

See also
--------

- CSS key concepts:
  - [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
  - [At-rules](at-rule.md)
  - [Comments](comments.md)
  - [Specificity](specificity.md)
  - [Inheritance](inheritance.md)
  - [Box model](introduction_to_the_css_box_model.md)
  - [Layout modes](layout_mode.md)
  - [Visual formatting models](visual_formatting_model.md)
  - [Margin collapsing](mastering_margin_collapsing.md)
  - Values
    - [Initial values](initial_value.md)
    - [Computed values](computed_value.md)
    - [Used values](used_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/actual_value>

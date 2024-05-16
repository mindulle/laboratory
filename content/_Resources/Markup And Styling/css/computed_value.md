Computed value
==============

The **computed value** of a
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is the
value that is transferred from parent to child during inheritance. It is
calculated from the [specified value](specified_value.md) by:

1. Handling the special values [`inherit`](inherit.md),
    [`initial`](initial.md), [`revert`](revert.md),
    [`revert-layer`](revert-layer.md), and [`unset`](unset.md).
2. Doing the computation needed to reach the value described in the
    \"Computed value\" line in the property\'s definition table.

The computation needed to reach a property\'s computed value typically
involves converting relative values (such as those in `em` units or
percentages) to absolute values. For example, if an element has
specified values `font-size: 16px` and `padding-top: 2em`, then the
computed value of `padding-top` is `32px` (double the font size).

However, for some properties (those where percentages are relative to
something that may require layout to determine, such as `width`,
`margin-right`, `text-indent`, and `top`), percentage-specified values
turn into percentage-computed values. Additionally, unitless numbers
specified on the `line-height` property become the computed value, as
specified. The relative values that remain in the computed value become
absolute when the [used value](used_value.md) is determined.

**Note:** The
[`getComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
DOM API returns the [resolved value](resolved_value.md), which may either
be the computed value or the [used value](used_value.md), depending on the
property.

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  computed-value]](https://www.w3.org/TR/CSS22/cascade.html#computed-value)

  -----------------------------------------------------------------------------------

See also
--------

- [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
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
    - [Used values](used_value.md)
    - [Actual values](actual_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/computed_value>

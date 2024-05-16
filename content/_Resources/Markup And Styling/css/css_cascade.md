CSS cascade and inheritance
===========================

The **CSS cascade and inheritance** module defines the rules for
assigning values to properties by way of cascading and inheritance. This
module specifies the rules for finding the specified value for all
properties on all elements.

One of the fundamental design principles of CSS is cascading of rules.
It allows several style sheets to influence the presentation of a
document. CSS property-value declarations define how a document is
rendered. Multiple declarations may set different values for the same
element and property combination, but only one value can be applied to
any CSS property. The CSS cascade module defines how these conflicts are
resolved.

The opposite also occurs. Sometimes there are no declarations defining
the value of a property. The CSS cascade module defines how these
missing values should be set via inheritance or from the property\'s
initial value.

**Note:** The rules for finding the specified values in the page context
and its margin boxes are described in the [](css_paged_media.md).

Reference
---------

### Properties

- [`all`](all.md)

### At-rules

- [`@import`](@import.md)
- [`@layer`](@layer.md)

### Keywords

- [`initial`](initial.md)
- [`inherit`](inherit.md)
- [`revert`](revert.md)
- [`revert-layer`](revert-layer.md) [Experimental]
- [`unset`](unset.md)
- [`!important`](important.md) flag

### Interfaces

- [`CSSLayerBlockRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSLayerBlockRule)
- [`CSSGroupingRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule)
- [`CSSLayerStatementRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSLayerStatementRule)
- [`CSSRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule)

### Key concepts and definitions

- [`Specificity`](specificity.md)
- [Cascade origin and importance](cascade.md)
- [Values](value_definition_syntax.md)
  - [actual value](actual_value.md)
  - [computed value](computed_value.md)
  - [initial value](initial_value.md)
  - [resolved value](resolved_value.md)
  - [specified value](specified_value.md)
  - [used value](used_value.md)
- [Origin types](cascade.md#origin_types)
  - [user-agent origin](cascade.md#user-agent_stylesheets)
  - [author origin](cascade.md#author_stylesheets)
  - [user origin](cascade.md#user_stylesheets)
- [Declaring layers](@import.md#importing_css_rules_into_a_cascade_layer)
  - [named
        layer](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_layers#the_layer_statement_at-rule_for_named_layers)
  - [anonymous
        layer](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_layers#the-layer-block-at-rule-for-named-and-anonymous-layers)
- Glossary: [style
    origin](https://developer.mozilla.org/en-US/docs/Glossary/Style_origin)

Guides
------

[Introducing the CSS Cascade](cascade.md)

:   Guide to the cascade algorithm that defines how user agents combine
    property values originating from different sources.

[Learn: Cascade, specificity, and inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)

:   The most fundamental concepts of CSS --- the cascade, specificity,
    and inheritance --- which control how CSS is applied to HTML and how
    conflicts are resolved.

[Learn: Cascade layers](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_layers)

:   Introduction to [cascade layers](@layer.md), a more advanced feature
    that builds on the fundamental concepts of the [](cascade.md) and [CSS specificity](specificity.md).

[CSS inheritance](inheritance.md)

:   A guide to CSS inheritance.

Related concepts
----------------

- [Element-attached
    styles](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/style)
- [Inline styles and the cascade](cascade.md#inline_styles)
- [](@import.md#importing_css_rules_conditional_on_media_queries)

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Cascading and Inheritance Level 4\
  ](https://drafts.csswg.org/css-cascade/)

[CSS Cascading and Inheritance Level 5\
  ](https://drafts.csswg.org/css-cascade-5/)
  -----------------------------------------------------------------------

See also
--------

- [CSS selectors module](css_selectors.md)
- [CSS pseudo-elements module](css_pseudo-elements.md)
- [CSS paged media module](css_paged_media.md)
- [CSS conditional rules module](css_conditional_rules.md)
- [CSS nesting module](css_nesting.md)
- [Shorthand properties](shorthand_properties.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade>

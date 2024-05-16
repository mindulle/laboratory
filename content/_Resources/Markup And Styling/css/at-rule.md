At-rules
========

**At-rules** are [CSS statements](_Resources/Markup%20And%20Styling/css/syntax.md#css_statements) that instruct
CSS how to behave. They begin with an at sign, \'`@`\'
(`U+0040 COMMERCIAL AT`), followed by an identifier and includes
everything up to the next semicolon, \'`;`\' (`U+003B SEMICOLON`), or
the next [CSS block](_Resources/Markup%20And%20Styling/css/syntax.md#css_declarations_blocks), whichever comes
first.

Syntax
------

### Regular

[css]

```css
/* General structure */
@identifier (RULE);

/* Example: tells browser to use UTF-8 character set */
@charset "utf-8";
```

There are several regular at-rules, designated by their identifiers,
each with a different syntax:

- [`@charset`](@charset.md) --- Defines the character set used by the
    style sheet.
- [`@import`](@import.md) --- Tells the CSS engine to include an external
    style sheet.
- [`@namespace`](@namespace.md) --- Tells the CSS engine that all its
    content must be considered prefixed with an XML namespace.

### Nested

[css]

```css
@identifier (RULE) {
}
```

A subset of nested statements, which can be used as a statement of a
style sheet as well as inside of conditional group rules.

- [`@media`](@media.md) --- A conditional group rule that will apply its
    content if the device meets the criteria of the condition defined
    using a *media query*.
- [`@supports`](@supports.md) --- A conditional group rule that will
    apply its content if the browser meets the criteria of the given
    condition.
- [`@document`](@document.md) [Deprecated] --- A
    conditional group rule that will apply its content if the document
    in which the style sheet is applied meets the criteria of the given
    condition.
- [`@page`](@page.md) --- Describes the aspect of layout changes that
    will be applied when printing the document.
- [`@font-face`](@font-face.md) --- Describes the aspect of an external
    font to be downloaded.
- [`@keyframes`](@keyframes.md) --- Describes the aspect of intermediate
    steps in a CSS animation sequence.
- [`@counter-style`](@counter-style.md) --- Defines specific counter
    styles that are not part of the predefined set of styles.
- [`@font-feature-values`](@font-feature-values.md) (plus `@swash`,
    `@ornaments`, `@annotation`, `@stylistic`, `@styleset` and
    `@character-variant`) --- Define common names in
    [`font-variant-alternates`](font-variant-alternates.md) for feature
    activated differently in OpenType.
- [`@property`](@property.md) --- Describes the aspect of custom
    properties and variables.
- [`@layer`](@layer.md) -- Declares a cascade layer and defines the order
    of precedence in case of multiple cascade layers.

Conditional group rules
-----------------------

Much like the values of properties, each at-rule has a different syntax.
Nevertheless, several of them can be grouped into a special category
named **conditional group rules**. These statements share a common
syntax and each of them can include *nested statements*---either
*rulesets* or *nested at-rules*. Furthermore, they all convey a common
semantic meaning---they all link some type of condition, which at any
time evaluates to either **true** or **false**. If the condition
evaluates to **true**, then all of the statements within the group will
be applied.

Conditional group rules are:

- [`@media`](@media.md),
- [`@supports`](@supports.md),
- [`@document`](@document.md). *(deferred to Level 4 of CSS Spec)*

Since each conditional group may also contain nested statements, there
may be an unspecified amount of nesting.

Nesting \@layer with CSS nesting
--------------------------------

[Cascade layers](@layer.md) can be nested to [](@layer.md#nesting_layers). These are joined with a `.`(dot). This
can also be achieved using [](nesting_at-rules.md#nesting_cascade_layers_layer).

Index
-----

- [`@charset`](@charset.md)
- [`@color-profile`](@color-profile.md)
- [`@container`](@container.md)
- [`@counter-style`](@counter-style.md)
- [`@document`](@document.md) [Deprecated]
- [`@font-face`](@font-face.md)
- [`@font-feature-values`](@font-feature-values.md)
- [`@font-palette-values`](@font-palette-values.md)
- [`@import`](@import.md)
- [`@keyframes`](@keyframes.md)
- [`@layer`](@layer.md)
- [`@media`](@media.md)
- [`@namespace`](@namespace.md)
- [`@page`](@page.md)
- [`@property`](@property.md)
- [`@supports`](@supports.md)

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Conditional Rules Module Level 3\
  ](https://drafts.csswg.org/css-conditional-3/)

[Compatibility Standard\
  [\#
  css-at-rules]](https://compat.spec.whatwg.org/#css-at-rules)
  -----------------------------------------------------------------------

See also
--------

- CSS key concepts:
  - [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
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
    - [Actual values](actual_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)
  - [CSS nesting module](css_nesting.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule>

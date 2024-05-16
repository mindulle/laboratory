Specified value
===============

The **specified value** of a
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is the
value it receives from the document\'s style sheet. The specified value
for a given property is determined according to the following rules:

1. If the document\'s style sheet explicitly specifies a value for the
    property, the given value will be used.
2. If the document\'s style sheet doesn\'t specify a value but it is an
    inherited property, the value will be taken from the parent element.
3. If none of the above pertain, the element\'s [](initial_value.md) will be used.

Examples
--------

### HTML

[html]

```html
<p>My specified color is given explicitly in the CSS.</p>

<div>
  The specified values of all my properties default to their initial values,
  because none of them are given in the CSS.
</div>

<div class="fun">
  <p>
    The specified value of my font family is not given explicitly in the CSS, so
    it is inherited from my parent. However, the border is not an inheriting
    property.
  </p>
</div>
```

### CSS

[css]

```css
.fun {
  border: 1px dotted pink;
  font-family: fantasy;
}

p {
  color: green;
}
```

### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  specified-value]](https://www.w3.org/TR/CSS22/cascade.html#specified-value)

  -------------------------------------------------------------------------------------

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
    - [Actual values](actual_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/specified_value>

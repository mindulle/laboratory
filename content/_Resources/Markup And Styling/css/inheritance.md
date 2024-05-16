Inheritance
===========

In CSS, **inheritance** controls what happens when no value is specified
for a property on an element.

CSS properties can be categorized in two types:

- **inherited properties**, which by default are set to the [](computed_value.md) of the parent element
- **non-inherited properties**, which by default are set to [](initial_value.md) of the property

Refer to [any CSS property](reference#index) definition to see whether a
specific property inherits by default (\"Inherited: yes\") or not
(\"Inherited: no\").

Inherited properties
--------------------

When no value for an **inherited property** has been specified on an
element, the element gets the [computed value](computed_value.md) of that
property on its parent element. Only the root element of the document
gets the [initial value](initial_value.md) given in the property\'s
summary.

A typical example of an inherited property is the [`color`](_Resources/Markup%20And%20Styling/css/color.md)
property. Consider the following style rules and the markup:

[css]

```css
p {
  color: green;
}
```

[html]

```html
<p>This paragraph has <em>emphasized text</em> in it.</p>
```

The words \"emphasized text\" will appear green, since the `em` element
has inherited the value of the [`color`](_Resources/Markup%20And%20Styling/css/color.md) property from the `p`
element. It does *not* get the initial value of the property (which is
the color that is used for the root element when the page specifies no
color).

Non-inherited properties
------------------------

When no value for a **non-inherited property** has been specified on an
element, the element gets the [initial value](initial_value.md) of that
property (as specified in the property\'s summary).

A typical example of a non-inherited property is the [`border`](border.md)
property. Consider the following style rules and the markup:

[css]

```css
p {
  border: medium solid;
}
```

[html]

```html
<p>This paragraph has <em>emphasized text</em> in it.</p>
```

The words \"emphasized text\" will not have another border (since the
initial value of [`border-style`](border-style.md) is `none`).

Notes
-----

The [`inherit`](inherit.md) keyword allows authors to explicitly specify
inheritance. It works on both inherited and non-inherited properties.

You can control inheritance for all properties at once using the
[`all`](all.md) shorthand property, which applies its value to all
properties. For example:

[css]

```css
p {
  all: revert;
  font-size: 200%;
  font-weight: bold;
}
```

This reverts the style of the paragraphs\' [`font`](font.md) property to
the user agent\'s default unless a user stylesheet exists, in which case
that is used instead. Then it doubles the font size and applies a
[`font-weight`](_Resources/Markup%20And%20Styling/css/font-weight.md) of `"bold"`.

### Overriding inheritance, an example

Using our previous example with [`border`](border.md), if we explicitly set
the inheritance with `inherit`, we get the following:

[css]

```css
p {
  border: medium solid;
}

em {
  border: inherit;
}
```

[html]

```html
<p>This paragraph has <em>emphasized text</em> in it.</p>
```

We can see here another border around the word \"emphasized text\".

See also
--------

- CSS values for controlling inheritance: [`inherit`](inherit.md),
    [`initial`](initial.md), [`revert`](revert.md),
    [`revert-layer`](revert-layer.md), and [`unset`](unset.md)
- [Introducing the CSS cascade](cascade.md)
- [Cascade, specificity, and
    inheritance](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Cascade_and_inheritance)
- CSS key concepts:
  - [CSS syntax](_Resources/Markup%20And%20Styling/css/syntax.md)
  - [At-rules](at-rule.md)
  - [Comments](comments.md)
  - [Specificity](specificity.md)
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
https://developer.mozilla.org/en-US/docs/Web/CSS/Inheritance>

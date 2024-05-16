Mastering margin collapsing
===========================

The [top](margin-top.md) and [bottom](margin-bottom.md) margins of
blocks are sometimes combined (collapsed) into a single margin whose
size is the largest of the individual margins (or just one of them, if
they are equal), a behavior known as **margin collapsing**. Note that
the margins of [floating](float.md) and [](position.md#types_of_positioning) elements never collapse.

Margin collapsing occurs in three basic cases:

[Adjacent siblings](#adjacent_siblings)

:   The margins of adjacent siblings are collapsed (except when the
    latter sibling needs to be [cleared](clear.md) past floats).

[No content separating parent and descendants](#no_content_separating_parent_and_descendants)

:   If there is no border, padding, inline part, [block formatting
    context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
    created, or *[clearance](clear.md)* to separate the
    [`margin-top`](margin-top.md) of a block from the
    [`margin-top`](margin-top.md) of one or more of its descendant
    blocks; or no border, padding, inline content,
    [`height`](_Resources/Markup%20And%20Styling/css/height.md), or [`min-height`](min-height.md) to separate
    the [`margin-bottom`](margin-bottom.md) of a block from the
    [`margin-bottom`](margin-bottom.md) of one or more of its descendant
    blocks, then those margins collapse. The collapsed margin ends up
    outside the parent.

[Empty blocks](#empty_blocks)

:   If there is no border, padding, inline content,
    [`height`](_Resources/Markup%20And%20Styling/css/height.md), or [`min-height`](min-height.md) to separate
    a block\'s [`margin-top`](margin-top.md) from its
    [`margin-bottom`](margin-bottom.md), then its top and bottom margins
    collapse.

Some things to note:

- More complex margin collapsing (of more than two margins) occurs
    when the above cases are combined.
- These rules apply even to margins that are zero, so the margin of a
    descendant ends up outside its parent (according to the rules above)
    whether or not the parent\'s margin is zero.
- When negative margins are involved, the size of the collapsed margin
    is the sum of the largest positive margin and the smallest (most
    negative) negative margin.
- When all margins are negative, the size of the collapsed margin is
    the smallest (most negative) margin. This applies to both adjacent
    elements and nested elements.
- Collapsing margins is only relevant in the vertical direction.
- Margins don\'t collapse in a container with `display` set to `flex`
    or `grid`.

Examples
--------

### HTML

[html]

```html
<p>The bottom margin of this paragraph is collapsed …</p>
<p>
  … with the top margin of this paragraph, yielding a margin of
  <code>1.2rem</code> in between.
</p>

<div>
  This parent element contains two paragraphs!
  <p>
    This paragraph has a <code>.4rem</code> margin between it and the text
    above.
  </p>
  <p>
    My bottom margin collapses with my parent, yielding a bottom margin of
    <code>2rem</code>.
  </p>
</div>

<p>I am <code>2rem</code> below the element above.</p>
```

### CSS

[css]

```css
div {
  margin: 2rem 0;
  background: lavender;
}

p {
  margin: 0.4rem 0 1.2rem 0;
  background: yellow;
}
```

### Result

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
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_box_model/Mastering_margin_collapsing>

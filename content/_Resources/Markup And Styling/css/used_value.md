Used value
==========

The **used value** of a
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is its
value after all calculations have been performed on the [](computed_value.md).

After the [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) has
finished its calculations, every CSS property has a used value. The used
values of dimensions (e.g., [`width`](_Resources/Markup%20And%20Styling/css/width.md),
[`line-height`](line-height.md)) are in pixels. The used values of
shorthand properties (e.g., [`background`](background.md)) are consistent
with those of their component properties (e.g.,
[`background-color`](background-color.md) or
[`background-size`](background-size.md)) and with [`position`](position.md)
and [`float`](float.md).

**Note:** The
[`getComputedStyle()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
DOM API returns the [resolved value](resolved_value.md), which may either
be the [computed value](computed_value.md) or the used value, depending on
the property.

Example
-------

This example computes and displays the used `width` value of three
elements (updates on resize):

### HTML

[html]

```html
<div id="no-width">
  <p>No explicit width.</p>
  <p class="show-used-width">..</p>

  <div id="width-50">
    <p>Explicit width: 50%.</p>
    <p class="show-used-width">..</p>

    <div id="width-inherit">
      <p>Explicit width: inherit.</p>
      <p class="show-used-width">..</p>
    </div>
  </div>
</div>
```

### CSS

[css]

```css
#no-width {
  width: auto;
}

#width-50 {
  width: 50%;
}

#width-inherit {
  width: inherit;
}

/* Make results easier to see */
div {
  border: 1px solid red;
  padding: 8px;
}
```

### JavaScript

[js]

```js
function updateUsedWidth(id) {
  const div = document.getElementById(id);
  const par = div.querySelector(".show-used-width");
  const wid = window.getComputedStyle(div)["width"];
  par.textContent = `Used width: $.`;
}

function updateAllUsedWidths() {
  updateUsedWidth("no-width");
  updateUsedWidth("width-50");
  updateUsedWidth("width-inherit");
}

updateAllUsedWidths();
window.addEventListener("resize", updateAllUsedWidths);
```

### Result

Difference from computed value
------------------------------

CSS 2.0 defined only *computed value* as the last step in a property\'s
calculation. Then, CSS 2.1 introduced the distinct definition of used
value. An element could then explicitly inherit a width/height of a
parent, whose computed value is a percentage. For CSS properties that
don\'t depend on layout (e.g., `display`, `font-size`, or
`line-height`), the computed values and used values are the same. The
following are the CSS 2.1 properties that do depend on layout, so they
have a different computed value and used value: (taken from [CSS 2.1
Changes: Specified, computed, and actual
values](https://www.w3.org/TR/CSS2/changes.html#q21.36)):

- `background-position`
- `bottom`, `left`, `right`, `top`
- `height`, `width`
- `margin-bottom`, `margin-left`, `margin-right`, `margin-top`
- `min-height`, `min-width`
- `padding-bottom`, `padding-left`, `padding-right`, `padding-top`
- `text-indent`

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  used-value]](https://www.w3.org/TR/CSS22/cascade.html#used-value)

  ---------------------------------------------------------------------------

See also
--------

- [`window.getComputedStyle`](https://developer.mozilla.org/en-US/docs/Web/API/Window/getComputedStyle)
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
    - **Used values**
    - [Actual values](actual_value.md)
  - [Value definition syntax](value_definition_syntax.md)
  - [Shorthand properties](shorthand_properties.md)
  - [Replaced elements](replaced_element.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/used_value>

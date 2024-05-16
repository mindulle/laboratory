CSS nesting and specificity
===========================

The [`specificity`](specificity.md) of the `&` nesting selector is
calculated using the largest specificity in the associated selector
list. This is identical to how specificity is calculated when using the
[`:is()`](../:is) function.

[html]

```html
<b class="foo">
  <c>Blue text</c>
</b>
```

`&` nesting syntax
------------------

[css]

```css
#a, b {
  & c {
    color: blue;
  }
}

.foo c {
  color: red;
}
```

`:is()` syntax
--------------

[css]

```css
:is(#a, b) {
  & c {
    color: blue;
  }
}

.foo c {
  color: red;
}
```

In this example, the id selector (`#a`) has a specificity of
[`1-0-0`](specificity.md#selector_weight_categories), while the type
selector (`b`) has a specificity of `0-0-1`. The [](nesting_selector.md) and `:is()` pseudo-class both take a
specificity of `1-0-0`, even though the `#a` id selector is never used.

The `.foo` class selector has a specificity of `0-1-0`. This makes the
total specificity `1-0-1` for `& c` and `0-1-1` for `.foo c`, meaning
that `color: blue;` wins out.

See Also
--------

- [CSS nesting](css_nesting.md) module
- [`&` nesting selector](nesting_selector.md)
- [Using CSS nesting](using_css_nesting.md)
- [Nesting at-rules](nesting_at-rules.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting/Nesting_and_specificity>

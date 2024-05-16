& nesting selector
==================

The CSS `&` explicitly states the relationship between parent and child
rules when using [CSS Nesting](css_nesting.md). Nested child rule selectors
are relative to the parent rule selectors, with the child rule component
having the same [specificity](nesting_and_specificity.md)
weight as if they were within [`:is()`](:is).

Syntax
------

[css]

```css
parentRule {
  /* parent rule style properties */
  & childRule {
    /* child rule style properties */
  }
}
```

### `&` nesting selector and whitespace

In this example, nesting is done without the `&`. When the browser
parses the nested selectors, it automatically adds whitespace between
the selectors to create a new CSS selector rule.

[css]

```css
.parent-rule {
  /* parent rule properties */
  .child-rule {
    /* child rule properties */
  }
}

/* the browser parses this as */
.parent-rule {
  /* parent rule style properties */
}

.parent-rule .child-rule {
  /* style properties for .child-rule descendants for .parent-rule ancestors */
}
```

When the nested rule needs to be attached (with no whitespace) to the
parent rule, such as when using a [`pseudo class`](pseudo-classes.md) or
creating [](selector_structure.md#compound_selector), the `&`
must be immediately prepended to achieve the desired effect.

Consider an example where we want to style an element, providing styles
to be applied at all times, and also nesting some styles to be applied
only on hover. If the `&` is not included, whitespace is added and we
end up with a ruleset that applies the nested styles to any *hovered
descendant of the parent rule selector*. This is not what we wanted.

[css]

```css
.parent-rule {
  /* parent rule properties */
  :hover {
    /* child rule properties */
  }
}

/* the browser parses this as */
.parent-rule {
  /* parent rule properties */
}

.parent-rule *:hover {
  /* child rule properties */
}
```

With the `&` added with no whitespace, the elements matched by the
parent rule will be styled when hovered.

[css]

```css
.parent-rule {
  /* parent rule properties */
  &:hover {
    /* child rule properties */
  }
}

/* the browser parses this as */
.parent-rule {
  /* parent rule properties */
}

.parent-rule:hover {
  /* child rule properties */
}
```

Appending the `&` nesting selector
----------------------------------

The `&` nesting selector can also be appended to reverse the context of
the rules.

[css]

```css
.card {
  /* .card styles */
  .featured & {
    /* .featured .card styles */
  }
}

/* the browser parses this as */
.card {
  /* .card styles */
}

.featured .card {
  /* .featured .card styles */
}
```

The `&` nesting selector can be placed multiple times:

[css]

```css
.card {
  /* .card styles */
  .featured & & & {
    /* .featured .card .card .card styles */
  }
}

/* the browser parses this as */
.card {
  /* .card styles */
}

.featured .card .card .card {
  /* .featured .card .card .card styles */
}
```

Examples
--------

Both of the following examples produce the same output. The first one
uses normal CSS styles and the second one uses the `&` nesting selector.

### Normal CSS styles

This example uses normal CSS styling.

#### HTML

[html]

```html
<p class="example">
  This paragraph <a href="#">contains a link</a>, try hovering or focusing it.
</p>
```

#### CSS

[css]

```css
.example {
  font-family: system-ui;
  font-size: 1.2rem;
}

.example > a {
  color: tomato;
}

.example > a:hover,
.example > a:focus {
  color: ivory;
  background-color: tomato;
}
```

#### Result

### Nested CSS styles

This example uses nested CSS styling.

#### HTML

[html]

```html
<p class="example">
  This paragraph <a href="#">contains a link</a>, try hovering or focusing it.
</p>
```

#### CSS

[css]

```css
.example {
  font-family: system-ui;
  font-size: 1.2rem;
  & > a {
    color: tomato;
    &:hover,
    &:focus {
      color: ivory;
      background-color: tomato;
    }
  }
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Nesting Module\
  [\#
  nest-selector]](https://drafts.csswg.org/css-nesting/#nest-selector)

  ------------------------------------------------------------------------------

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`Nesting_selector`

112Does not support nested rules that start with a type selector.

112Does not support nested rules that start with a type selector.

117

No

98Does not support nested rules that start with a type selector.

16.5Does not support nested rules that start with a type selector.

112Does not support nested rules that start with a type selector.

112Does not support nested rules that start with a type selector.

117

NoDoes not support nested rules that start with a type selector.

16.5Does not support nested rules that start with a type selector.

NoDoes not support nested rules that start with a type selector.

See also
--------

- [Using CSS nesting](using_css_nesting.md)
- [CSS nesting](css_nesting.md) module
- [CSS selectors](css_selectors.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/Nesting_selector>

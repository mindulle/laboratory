CSS nesting at-rules
====================

Any [at-rule](at-rule.md) whose body contains style rules can be nested
inside another style rule using CSS nesting. Style rules nested inside
at-rules take their nesting selector definition from the nearest
ancestor style rule. Properties can be directly included inside a nested
at-rule, acting as if they were nested in a `&` block.

at-rules that can be nested
---------------------------

- [`@media`](@media.md)
- [`@supports`](@supports.md)
- [`@layer`](@layer.md)
- [`@scope`]
- [`@container`](@container.md)

Examples
--------

### Nesting `@media` at-rule

In this example we see three blocks of CSS. The first one shows how to
write typical at-rule nesting, the second is an expanded way of writing
the nesting as the browser parses it, and the third one shows the
non-nested equivalent.

#### Nested CSS

[css]

```css
.foo {
  display: grid;
  @media (orientation: landscape) {
    grid-auto-flow: column;
  }
}
```

#### Expanded nested CSS

[css]

```css
.foo {
  display: grid;
  @media (orientation: landscape) {
    & {
      grid-auto-flow: column;
    }
  }
}
```

#### Non-nested equivalent

[css]

```css
.foo {
  display: grid;
}

@media (orientation: landscape) {
  .foo {
    grid-auto-flow: column;
  }
}
```

### Multiple nested `@media` at-rules

At-rules can be nested within other at-rules. Below you can see an
example of this, and how it would be written without nesting.

#### Nested at-rules

[css]

```css
.foo {
  display: grid;
  @media (orientation: landscape) {
    grid-auto-flow: column;
    @media (min-width > 1024px) {
      max-inline-size: 1024px;
    }
  }
}
```

#### Non-nested equivalent

[css]

```css
.foo {
  display: grid;
}
@media (orientation: landscape) {
  .foo {
    grid-auto-flow: column;
  }
}
@media (orientation: landscape) and (min-width > 1024px) {
  .foo {
    max-inline-size: 1024px;
  }
}
```

### Nesting Cascade Layers (`@layer`)

[Cascade Layers](@layer.md) can be nested to [](@layer.md#nesting_layers). These are joined with a
`.`(dot).

#### Defining the parent & child layers

We start by defining the named cascade layers, prior to using them,
without any style assignments.

[css]

```css
@layer base {
  @layer support;
}
```

#### Assigning rules to layers with nesting

Here the `.foo` selector assigns its rules to the **base** `@layer`. The
nested **support** `@layer` creates the `base.support` sub-layer, and
the `&` nesting selector is used to create the rules for the `.foo .bar`
selector .

[css]

```css
.foo {
  @layer base {
    block-size: 100%;
    @layer support {
      & .bar {
        min-block-size: 100%;
      }
    }
  }
}
```

#### Equivalent without nesting

[css]

```css
@layer base {
  .foo {
    block-size: 100%;
  }
}
@layer base.support {
  .foo .bar {
    min-block-size: 100%;
  }
}
```

See Also
--------

- [CSS Nesting](css_nesting.md) module
- [`&` nesting selector](nesting_selector.md)
- [Using CSS nesting](using_css_nesting.md)
- [Nesting and specificity](nesting_and_specificity.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_nesting/Nesting_at-rules>

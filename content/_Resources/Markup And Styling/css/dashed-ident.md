\<dashed-ident\>
================

The `<dashed-ident>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) denotes an arbitrary string used as an
[identifier](https://developer.mozilla.org/en-US/docs/Glossary/Identifier).

Syntax
------

The syntax of `<dashed-ident>` is similar to CSS identifiers (such as
property names), except that it is
[case-sensitive](https://en.wikipedia.org/wiki/Case_sensitivity). It
starts with two dashes, followed by the user-defined identifier.

The double dash at the beginning makes them easily identifiable when
reading through a CSS code block, and helps to avoid name clashes with
standard CSS keywords.

Just like [`<custom-ident>`](custom-ident.md) `<dashed-ident>`s are defined
by the user, but unlike `<custom-ident>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) will never
define a `<dashed-ident>`.

Examples
--------

### Using with CSS custom properties

When `<dashed-ident>` is used with [](using_css_custom_properties.md), the property is declared first
and then used within a [CSS var() function](var().md).

[css]

```css
html {
  --primary-color: red;
  --secondary-color: blue;
  --tertiary-color: green;
}

h1,
h4 {
  color: var(--primary-color);
}

h2,
h5 {
  color: var(--secondary-color);
}

h3,
h6 {
  color: var(--tertiary-color);
}
```

### Using with \@color-profile

When `<dashed-ident>` is used with the [\@color-profile](@color-profile.md)
at-rule, the at-rule is declared first and then used within a [](_Resources/Markup%20And%20Styling/css/color_value/color.md).

[css]

```css
@color-profile --my-color-profile {
  src: url("https://example.org/SWOP2006_Coated5v2.icc");
}

.header {
  background-color: color(--my-color-profile 0% 70% 20% 0%);
}
```

### Using with \@font-palette-values

When `<dashed-ident>` is used with the
[\@font-palette-values](@font-palette-values.md) at-rule, the at-rule is
declared first and then used as the value for the
[font-palette](font-palette.md) property.

[css]

```css
@font-palette-values --my-palette {
  font-family: Bixa;
  base-palette: 1;
  override-colors: 0 #ff0000;
}

h1,
h2,
h3,
h4 {
  font-palette: --my-palette;
}
```

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  dashed-idents]](https://drafts.csswg.org/css-values/#dashed-idents)

  -----------------------------------------------------------------------------

Browser compatibility
---------------------

See also
--------

- [\<ident\>](ident.md)
- [\<custom-ident\>](custom-ident.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/dashed-ident>

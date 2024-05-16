math-shift
==========

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `math-shift` property indicates whether superscripts inside MathML
formulas should be raised by a normal or compact shift.

Syntax
------

[css]

```css
/* Keyword values */
math-shift: normal;
math-shift: compact;

/* Global values */
math-shift: inherit;
math-shift: initial;
math-shift: revert;
math-shift: revert-layer;
math-shift: unset;
```

### Values

[`normal`](#normal)

:   The initial value, indicates normal rendering. Superscripts in
    MathML formulas use the
    [superscriptShiftUp](https://w3c.github.io/mathml-core/#dfn-superscriptshiftup)
    parameter from the OpenType MATH table.

[`compact`](#compact)

:   Indicates compact rendering. Superscripts in MathML formulas use the
    [superscriptShiftUpCramped](https://w3c.github.io/mathml-core/#dfn-superscriptshiftupcramped)
    parameter from the OpenType MATH table, which is generally smaller.

Formal definition
-----------------

  ---------------------------------- ----------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- ----------------

Formal syntax
-------------

```
math-shift = 
  normal   |
  compact  
```

Examples
--------

### CSS

[css]

```css
math {
  math-shift: compact;
}
```

### MathML

The following MathML displays two versions of \"x squared\" using a font
with an OpenType MATH table. Browser implementing the `math-shift`
property should raise the superscripts using slightly different shifts.

[html]

```html
<math style="font-size: 64pt;">
  <msup style="math-shift: normal">
    <mi>x</mi>
    <mn>2</mn>
  </msup>
  <msup style="math-shift: compact">
    <mi>x</mi>
    <mn>2</mn>
  </msup>
</math>
```

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [MathML Core\
  [\#
  the-math-shift]](https://w3c.github.io/mathml-core/#the-math-shift)

  -----------------------------------------------------------------------------

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

`math-shift`

109

109

No

No

95

No

109

109

No

74

No

21.0

See also
--------

- [`math-depth`](math-depth.md)
- [`font-size`](font-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/math-shift>

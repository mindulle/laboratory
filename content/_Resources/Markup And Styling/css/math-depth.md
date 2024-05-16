math-depth
==========

The `math-depth` property describes a notion of *depth* for each element
of a mathematical formula, with respect to the top-level container of
that formula. This is used to scale the computed value of the
[font-size](font-size.md) of elements when `font-size: math` is applied.

**Note:** `font-size: math` is the default for `<math>` elements in the
MathML Core [User Agent
stylesheet](https://w3c.github.io/mathml-core/#user-agent-stylesheet),
so it\'s not necessary to specify it explicitly.

Syntax
------

[css]

```css
/* Keyword values */
math-depth: auto-add;

/* Relative values */
math-depth: add(2);
math-depth: add(-2);

/* Absolute value */
math-depth: 4;

/* Global values */
math-depth: inherit;
math-depth: initial;
math-depth: revert;
math-depth: revert-layer;
math-depth: unset;
```

### Values

[`auto-add`](#auto-add)

:   Set to the inherited `math-depth` plus 1 when inherited
    [math-style](math-style.md) is `compact`.

[`add(`](#add)`<integer>`)

:   Set to the inherited `math-depth` plus the specified integer.

[`<integer>`](integer.md)

:   Set to the specified integer.

Formal definition
-----------------

  ---------------------------------- ----------------
  [Initial value](initial_value.md)     `0`
  Applies to                         all elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     Not animatable
  ---------------------------------- ----------------

Formal syntax
-------------

```
math-depth = 
  auto-add          |
  add( <integer> )  |
  <integer>         
```

Examples
--------

### Specifying a math depth

The following example shows the effect of changing the `math-depth`
property on the font size of subformulas. The numbers in each subformula
indicate the `math-depth` and scale factor applied.

The first `<mtext>` element is used as a reference to other subformulas
and has no specific styles applied. The second and third subformulas
have `math-depth` set to `auto-add` and show the effect of scaling
depending on the `math-style`.

The last two subformulas show the effect of setting `math-depth` to a
specific value.

#### HTML

[html]

```html
<p style="font-size: 3rem; margin: 1rem 0">
  <math>
    <mtext>0</mtext>

    <!-- auto-add value has no effect when math-style is normal -->
    <mrow style="math-style: normal">
      <mrow style="math-depth: auto-add">
        <mtext>0</mtext>
      </mrow>
    </mrow>

    <!-- the inherited math-style is compact, so math-depth is set to 1 -->
    <mrow style="math-depth: auto-add">
      <mtext>1</mtext>
    </mrow>

    <mrow style="math-depth: add(2)">
      <mtext>2</mtext>
      <mrow style="math-depth: add(-1)">
        <mtext>1</mtext>
      </mrow>
      <mrow style="math-depth: 0">
        <mtext>0</mtext>
      </mrow>
    </mrow>
  </math>
</p>
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------------------

  [MathML Core\
  [\#
  the-math-script-level-property]](https://w3c.github.io/mathml-core/#the-math-script-level-property)

  -------------------------------------------------------------------------------------------------------------

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

`math-depth`

109

109

117

No

95

No

109

109

117

74

No

21.0

See also
--------

- [`font-size`](font-size.md)
- [`math-style`](math-style.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/math-depth>

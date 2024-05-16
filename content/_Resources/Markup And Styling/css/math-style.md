math-style
==========

The `math-style` property indicates whether MathML equations should
render with normal or compact height.

Syntax
------

[css]

```css
/* Keyword values */
math-style: normal;
math-style: compact;

/* Global values */
math-style: inherit;
math-style: initial;
math-style: revert;
math-style: revert-layer;
math-style: unset;
```

### Values

[`normal`](#normal)

:   The initial value, indicates normal rendering.

[`compact`](#compact)

:   The math layout on descendants tries to minimize the logical height.

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
math-style = 
  normal   |
  compact  
```

Examples
--------

### Changing the style of a formula to compact

#### CSS

[css]

```css
math {
  math-style: normal;
}
.compact {
  math-style: compact;
}
```

#### HTML

[html]

```html
<p>
  Normal height
  <math>
    <mrow>
      <munderover>
        <mo>∑</mo>
        <mrow>
          <mi>n</mi>
          <mo>=</mo>
          <mn>1</mn>
        </mrow>
        <mrow>
          <mo>+</mo>
          <mn>∞</mn>
        </mrow>
      </munderover>
    </mrow>
  </math>
  and compact height
  <math class="compact">
    <mrow>
      <munderover>
        <mo>∑</mo>
        <mrow>
          <mi>n</mi>
          <mo>=</mo>
          <mn>1</mn>
        </mrow>
        <mrow>
          <mo>+</mo>
          <mn>∞</mn>
        </mrow>
      </munderover>
    </mrow>
  </math>
  equations.
</p>
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [MathML Core\
  [\#
  the-math-style-property]](https://w3c.github.io/mathml-core/#the-math-style-property)

  -----------------------------------------------------------------------------------------------

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

`math-style`

109

109

117

No

95

14.1

109

109

117

74

14.5

21.0

See also
--------

- [`math-depth`](math-depth.md)
- [`font-size`](font-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/math-style>

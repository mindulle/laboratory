z-index
=======

The `z-index` CSS property sets the z-order of a [positioned](position.md)
element and its descendants or flex and grid items. Overlapping elements
with a larger z-index cover those with a smaller one.

Try it
------

For a positioned box (that is, one with any `position` other than
`static`), the `z-index` property specifies:

1. The stack level of the box in the current [](stacking_context.md).
2. Whether the box establishes a local stacking context.

Syntax
------

[css]

```css
/* Keyword value */
z-index: auto;

/* <integer> values */
z-index: 0;
z-index: 3;
z-index: 289;
z-index: -1; /* Negative values to lower the priority */

/* Global values */
z-index: inherit;
z-index: initial;
z-index: revert;
z-index: revert-layer;
z-index: unset;
```

The `z-index` property is specified as either the keyword `auto` or an
`<integer>`.

### Values

[`auto`](#auto)

:   The box does not establish a new local stacking context. The stack
    level of the generated box in the current stacking context is `0`.

[`<integer>`](#integer)

:   This [`<integer>`](integer.md) is the stack level of the generated box
    in the current stacking context. The box also establishes a local
    stacking context. This means that the z-indexes of descendants are
    not compared to the z-indexes of elements outside this element.

Formal definition
-----------------

  ------------------------------------------------------------------------------------------ -------------------------------------
  [Initial value](initial_value.md)                                                             `auto`
  Applies to                                                                                 positioned elements
  [Inherited](inheritance.md)                                                                   no
  [Computed value](computed_value.md)                                                           as specified
  Animation type                                                                             an [integer](integer.md#interpolation)
  Creates [stacking context](stacking_context.md)   yes
  ------------------------------------------------------------------------------------------ -------------------------------------

Formal syntax
-------------

```
z-index = 
  auto       |
  <integer>  |
  inherit    
```

Examples
--------

### Visually layering elements

#### HTML

[html]

```html
<div class="wrapper">
  <div class="dashed-box">Dashed box</div>
  <div class="gold-box">Gold box</div>
  <div class="green-box">Green box</div>
</div>
```

#### CSS

[css]

```css
.wrapper {
  position: relative;
}

.dashed-box {
  position: relative;
  z-index: 1;
  border: dashed;
  height: 8em;
  margin-bottom: 1em;
  margin-top: 2em;
}
.gold-box {
  position: absolute;
  z-index: 3; /* put .gold-box above .green-box and .dashed-box */
  background: gold;
  width: 80%;
  left: 60px;
  top: 3em;
}
.green-box {
  position: absolute;
  z-index: 2; /* put .green-box above .dashed-box */
  background: lightgreen;
  width: 20%;
  left: 65%;
  top: -25px;
  height: 7em;
  opacity: 0.9;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\# z-index]](https://drafts.csswg.org/css2/#z-index)

  -----------------------------------------------------------------------

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

`z-index`

1

12

1

4

4

1

≤37

18

4

14

1

1.0

`negative_values`

1

12

3

4

4

1

≤37

18

4

14

1

1.0

See also
--------

- CSS [`position`](position.md) property
- [](understanding_z-index.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/z-index>

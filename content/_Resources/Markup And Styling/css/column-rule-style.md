column-rule-style
=================

The `column-rule-style`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the style of the line drawn between columns in a multi-column layout.

Try it
------

Syntax
------

[css]

```css
/* <'border-style'> values */
column-rule-style: none;
column-rule-style: hidden;
column-rule-style: dotted;
column-rule-style: dashed;
column-rule-style: solid;
column-rule-style: double;
column-rule-style: groove;
column-rule-style: ridge;
column-rule-style: inset;
column-rule-style: outset;

/* Global values */
column-rule-style: inherit;
column-rule-style: initial;
column-rule-style: revert;
column-rule-style: revert-layer;
column-rule-style: unset;
```

The `column-rule-style` property is specified as a single
`<'border-style'>` value.

### Values

[`<'border-style'>`](#border-style)

:   Is a keyword defined by [`border-style`](border-style.md) describing
    the style of the rule. The styling must be interpreted as in the
    collapsing border model.

Formal definition
-----------------

  ---------------------------------- -------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         multicol elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -------------------

Formal syntax
-------------

```
column-rule-style = 
  <line-style>  

<line-style> = 
  none    |
  hidden  |
  dotted  |
  dashed  |
  solid   |
  double  |
  groove  |
  ridge   |
  inset   |
  outset  
```

Examples
--------

### Setting a dashed column rule

#### HTML

[html]

```html
<p>
  This is a bunch of text split into three columns. The `column-rule-style`
  property is used to change the style of the line that is drawn between
  columns. Don't you think that's wonderful?
</p>
```

#### CSS

[css]

```css
p {
  column-count: 3;
  column-rule-style: dashed;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  [\# crs]](https://drafts.csswg.org/css-multicol/#crs)

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

`column-rule-style`

501

1212

523.5--74

10

1511.1

93

50≤37

5018

524

1411.1

91

5.01.0

See also
--------

- [Multiple-column
    Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [`column-rule`](column-rule.md)
- [`column-rule-width`](column-rule-width.md)
- [`column-rule-color`](column-rule-color.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-style>

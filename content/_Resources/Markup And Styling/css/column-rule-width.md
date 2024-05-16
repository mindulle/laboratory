column-rule-width
=================

The `column-rule-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the width of the line drawn between columns in a multi-column layout.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
column-rule-width: thin;
column-rule-width: medium;
column-rule-width: thick;

/* <length> values */
column-rule-width: 1px;
column-rule-width: 2.5em;

/* Global values */
column-rule-width: inherit;
column-rule-width: initial;
column-rule-width: revert;
column-rule-width: revert-layer;
column-rule-width: unset;
```

The `column-rule-width` property is specified as a single
`<'border-width'>` value.

### Values

[`<'border-width'>`](#border-width)

:   Is a keyword defined by [`border-width`](border-width.md) describing
    the width of the rule. It may be either a [`<length>`](length.md) or
    one of the `thin`, `medium`, or `thick` keywords.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `medium`
  Applies to                         multicol elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   the absolute length; `0` if the [`column-rule-style`](column-rule-style.md) is `none` or `hidden`
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
column-rule-width = 
  <line-width>  

<line-width> = 
  <length [0,∞]>  |
  thin            |
  medium          |
  thick           
```

Examples
--------

### Setting a thick column rule

#### HTML

[html]

```html
<p>
  This is a bunch of text split into three columns. The `column-rule-width`
  property is used to change the width of the line that is drawn between
  columns. Don't you think that's wonderful?
</p>
```

#### CSS

[css]

```css
p {
  column-count: 3;
  column-rule-style: solid;
  column-rule-width: thick;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  [\# crw]](https://drafts.csswg.org/css-multicol/#crw)

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

`column-rule-width`

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
- [`column-rule-style`](column-rule-style.md)
- [`column-rule-color`](column-rule-color.md)
- [`column-rule`](column-rule.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-rule-width>

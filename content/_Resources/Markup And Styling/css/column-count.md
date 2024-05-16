column-count
============

The `column-count`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property breaks
an element\'s content into the specified number of columns.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
column-count: auto;

/* <integer> value */
column-count: 3;

/* Global values */
column-count: inherit;
column-count: initial;
column-count: revert;
column-count: revert-layer;
column-count: unset;
```

### Values

[`auto`](#auto)

:   The number of columns is determined by other CSS properties, such as
    [`column-width`](column-width.md).

[`<integer>`](integer.md)

:   Is a strictly positive [`<integer>`](integer.md) describing the ideal
    number of columns into which the content of the element will be
    flowed. If the [`column-width`](column-width.md) is also set to a
    non-`auto` value, it merely indicates the maximum allowed number of
    columns.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         Block containers except table wrapper boxes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     an [integer](integer.md#interpolation)
  ---------------------------------- ---------------------------------------------

Formal syntax
-------------

```
column-count = 
  auto             |
  <integer [1,∞]>  
```

Examples
--------

### Splitting a paragraph across three columns

#### HTML

[html]

```html
<p class="content-box">
  This is a bunch of text split into three columns using the CSS `column-count`
  property. The text is equally distributed over the columns.
</p>
```

#### CSS

[css]

```css
.content-box {
  column-count: 3;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Multi-column Layout Module Level 1\
  [\# cc]](https://drafts.csswg.org/css-multicol/#cc)

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

`column-count`

501

1212

52

1.5--74Before version 37, multiple columns didn\'t work with
`display: table-caption` elements.

10

1511.1

93

50≤37

5018

52

4Before version 37, multiple columns didn\'t work with
`display: table-caption` elements.

1411.1

91

5.01.0

See also
--------

- [`column-width`](column-width.md), [`columns`](columns.md) shorthand
- [`column-rule-color`](column-rule-color.md),
    [`column-rule-style`](column-rule-style.md),
    [`column-rule-width`](column-rule-width.md),
    [`column-rule`](column-rule.md) shorthand
- [Multiple-column
    Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
    (Learn Layout)
- [Basic Concepts of Multicol](_Resources/Markup%20And%20Styling/css/css_multicol_layout/basic_concepts.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-count>

column-width
============

The `column-width`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the ideal column width in a multi-column layout. The container will have
as many columns as can fit without any of them having a width less than
the `column-width` value. If the width of the container is narrower than
the specified value, the single column\'s width will be smaller than the
declared column width.

Try it
------

This property can help you create responsive designs that fit different
screen sizes. Especially in the presence of the
[`column-count`](column-count.md) property (which has precedence), you must
specify all related length values to achieve an exact column width. In
horizontal text these are [`width`](_Resources/Markup%20And%20Styling/css/width.md),
[`column-width`](column-width.md), [`column-gap`](column-gap.md), and
[`column-rule-width`](column-rule-width.md).

Syntax
------

[css]

```css
/* Keyword value */
column-width: auto;

/* <length> values */
column-width: 60px;
column-width: 15.5em;
column-width: 3.3vw;

/* Global values */
column-width: inherit;
column-width: initial;
column-width: revert;
column-width: revert-layer;
column-width: unset;
```

The `column-width` property is specified as one of the values listed
below.

### Values

[`<length>`](length.md)

:   Indicates the optimal column width. The actual column width may
    differ from the specified value: it may be wider when necessary to
    fill available space, and narrower when the available space is too
    small. The value must be strictly positive or the declaration is
    invalid. Percentage values are also invalid.

[`auto`](#auto)

:   The width of the column is determined by other CSS properties, such
    as [`column-count`](column-count.md).

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         Block containers except table wrapper boxes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   the absolute length, zero or larger
  Animation type                     a [length](length.md#interpolation)
  ---------------------------------- ---------------------------------------------

Formal syntax
-------------

```
column-width = 
  auto                                |
  <length [0,∞]>                      |
  min-content                         |
  max-content                         |
  fit-content( <length-percentage> )  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting column width in pixels

#### HTML

[html]

```html
<p class="content-box">
  Lorem ipsum dolor sit amet, consectetuer adipiscing elit, sed diam nonummy
  nibh euismod tincidunt ut laoreet dolore magna aliquam erat volutpat. Ut wisi
  enim ad minim veniam, quis nostrud exercitation ullamcorper suscipit lobortis
  nisl ut aliquip ex ea commodo consequat.
</p>
```

#### CSS

[css]

```css
.content-box {
  column-width: 100px;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Box Sizing Module Level 3\
  [\#
  column-sizing]](https://drafts.csswg.org/css-sizing/#column-sizing)

[CSS Multi-column Layout Module Level 1\
  [\# cw]](https://drafts.csswg.org/css-multicol/#cw)
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

`column-width`

501

1212

50

1.5--74Before version 37, multiple columns didn\'t work with
`display: table-caption` elements.

10

1511.1

93

50≤37

5018

50

4Before version 37, multiple columns didn\'t work with
`display: table-caption` elements.

1511.1

91

5.01.0

See also
--------

- [Multiple-column
    Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
    (Learn Layout)
- [Basic Concepts of Multicol](_Resources/Markup%20And%20Styling/css/css_multicol_layout/basic_concepts.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-width>

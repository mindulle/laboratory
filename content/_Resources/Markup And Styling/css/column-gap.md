column-gap
==========

The `column-gap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the size of the gap
([gutter](https://developer.mozilla.org/en-US/docs/Glossary/Gutters))
between an element\'s columns.

Initially a part of [Multi-column Layout](css_multicol_layout.md), the
definition of `column-gap` has been broadened to include multiple layout
methods. Now specified in [Box Alignment](css_box_alignment.md), it may be
used in Multi-column, Flexible Box, and Grid layouts.

Early versions of the specification called this property
`grid-column-gap`, and to maintain compatibility with legacy websites,
browsers will still accept `grid-column-gap` as an alias for
`column-gap`.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
column-gap: normal;

/* <length> values */
column-gap: 3px;
column-gap: 2.5em;

/* <percentage> value */
column-gap: 3%;

/* Global values */
column-gap: inherit;
column-gap: initial;
column-gap: revert;
column-gap: revert-layer;
column-gap: unset;
```

The `column-gap` property is specified as one of the values listed
below.

### Values

[`normal`](#normal)

:   The browser\'s default spacing is used between columns. For
    multi-column layout this is specified as `1em`. For all other layout
    types it is 0.

[`<length>`](length.md)

:   The size of the gap between columns, defined as a
    [`<length>`](length.md). The [`<length>`](length.md) property\'s value
    must be non-negative.

[`<percentage>`](percentage.md)

:   The size of the gap between columns, defined as a
    [`<percentage>`](percentage.md). The [`<percentage>`](percentage.md)
    property\'s value must be non-negative.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         multi-column elements, flex containers, grid containers
  [Inherited](inheritance.md)           no
  Percentages                        refer to corresponding dimension of the content area
  [Computed value](computed_value.md)   as specified, with \<length\>s made absolute, and normal computing to zero except on multi-column elements
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- ------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
column-gap = 
  normal                     |
  <length-percentage [0,∞]>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Flex layout

In this example, a flex container contains six flex items of two
different widths (`200px` and `300px`), creating flex items that are not
laid out as a grid. The `column-gap` property is used to add horizontal
space between the adjacent flex items.

#### HTML

[html]

```html
<div class="flexbox">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

#### CSS

To create a flex container, we set its [`display`](display.md) property
value to `flex`. We then use the [`flex-flow`](flex-flow.md) shorthand
property to set the [`flex-direction`](flex-direction.md) to row (the
default) and [`flex-wrap`](flex-wrap.md) to `wrap`, allowing the flex items
to flow onto new lines if needed. By default, flex items stretch to be
as tall as their container. By setting a [`height`](_Resources/Markup%20And%20Styling/css/height.md), even the
empty flex items will be `100px` tall.

To better demonstrate the `column-gap` property, the flex items in this
example have two different width values. The width of the flex items is
set within the `<div>` flex items. We use the [`flex-basis`](flex-basis.md)
component of the [`flex`](flex.md) shorthand property to make all the flex
items `200px` wide. We then target every third flex item by using the
[`:nth-of-type(3n)`](:nth-of-type) selector, widening them to `300px`.

The `column-gap` value is set as `20px` on the flex container to create
a `20px` gap between the adjacent flex items in each row.

[css]

```css
.flexbox {
  display: flex;
  flex-flow: row wrap;
  height: 100px;
  column-gap: 20px;
}

.flexbox > div {
  border: 1px solid green;
  background-color: lime;
  flex: 200px;
}
div:nth-of-type(3n) {
  flex: 300px;
}
```

#### Result

**Note:** While there is horizontal space between adjacent flex items in
each flex row, there is no space between the rows. To set vertical space
between flex rows, you can specify a non-zero value for the
[`row-gap`](row-gap.md) property. The [`gap`](gap.md) shorthand property is
also available to set both the `row-gap` and `column-gap` in one
declaration, in that order.

### Grid layout

#### HTML

[html]

```html
<div id="grid">
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
  <div></div>
</div>
```

#### CSS

[css]

```css
#grid {
  display: grid;
  height: 100px;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: 100px;
  column-gap: 20px;
}

#grid > div {
  border: 1px solid green;
  background-color: lime;
}
```

#### Result

### Multi-column layout

#### HTML

[html]

```html
<p class="content-box">
  This is some multi-column text with a 40px column gap created with the CSS
  `column-gap` property. Don't you think that's fun and exciting? I sure do!
</p>
```

#### CSS

[css]

```css
.content-box {
  column-count: 3;
  column-gap: 40px;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\#
  column-row-gap]](https://drafts.csswg.org/css-align/#column-row-gap)

  [CSS Grid Layout Module Level 2\
  [\# gutters]](https://drafts.csswg.org/css-grid/#gutters)

[CSS Multi-column Layout Module Level 1\
  [\# column-gap]](https://drafts.csswg.org/css-multicol/#column-gap)
  ------------------------------------------------------------------------------

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

`column-gap`

1

12

1.5

10

11.1

3

4.4

18

4

11.1

2

1.0

`flex_context`

84

84

63

No

70

14.1

84

84

63

60

14.5

14.0

`grid_context`

6657

1616

6152

No

5344

1210.1

6657

6657

6152

4743

1210.3

9.06.0

`multicol_context`

501

1212

52

1.5--74Before Firefox 3, the default value for the `normal` keyword was
`0` and not `1em`.

10

371511.1--15

103

50≤37

5018

524

371411.1--14

103

5.01.0

See also
--------

- Related CSS properties: [`row-gap`](row-gap.md), [`gap`](gap.md)
- Grid Layout Guide: *[](basic_concepts_of_grid_layout.md#gutters)*
- Multi-column Layout Guide: *[](styling_columns.md)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/column-gap>

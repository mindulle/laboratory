row-gap
=======

The `row-gap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the size of the gap
([gutter](https://developer.mozilla.org/en-US/docs/Glossary/Gutters))
between an element\'s rows.

Early versions of the specification called this property `grid-row-gap`,
and to maintain compatibility with legacy websites, browsers will still
accept `grid-row-gap` as an alias for `row-gap`.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
row-gap: 20px;
row-gap: 1em;
row-gap: 3vmin;
row-gap: 0.5cm;

/* <percentage> value */
row-gap: 10%;

/* Global values */
row-gap: inherit;
row-gap: initial;
row-gap: revert;
row-gap: revert-layer;
row-gap: unset;
```

### Values

[`<length-percentage>`](#length-percentage)

:   Is the width of the gutter separating the rows.
    [`<percentage>`](percentage.md) values are relative to the dimension of
    the element.

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
row-gap = 
  normal                     |
  <length-percentage [0,∞]>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Flex layout

#### HTML

[html]

```html
<div id="flexbox">
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
#flexbox {
  display: flex;
  flex-wrap: wrap;
  width: 300px;
  row-gap: 20px;
}

#flexbox > div {
  border: 1px solid green;
  background-color: lime;
  flex: 1 1 auto;
  width: 100px;
  height: 50px;
}
```

#### Result

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
  height: 200px;
  grid-template-columns: 150px 1fr;
  grid-template-rows: repeat(3, 1fr);
  row-gap: 20px;
}

#grid > div {
  border: 1px solid green;
  background-color: lime;
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

`row-gap`

47

16

52

No

34

10.1

47

47

52

34

10.3

5.0

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

See also
--------

- Related CSS properties: [`column-gap`](column-gap.md), [`gap`](gap.md)
- Grid Layout Guide: *[](basic_concepts_of_grid_layout.md#gutters)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/row-gap>

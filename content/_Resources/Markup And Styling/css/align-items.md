align-items
===========

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
`align-items` property sets the [`align-self`](align-self.md) value on all
direct children as a group. In Flexbox, it controls the alignment of
items on the [Cross
Axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis). In
Grid Layout, it controls the alignment of items on the Block Axis within
their [grid
area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas).

The interactive example below demonstrates some of the values for
`align-items` using grid layout.

Try it
------

Syntax
------

[css]

```css
/* Basic keywords */
align-items: normal;
align-items: stretch;

/* Positional alignment */
/* align-items does not take left and right values */
align-items: center;
align-items: start;
align-items: end;
align-items: flex-start;
align-items: flex-end;
align-items: self-start;
align-items: self-end;

/* Baseline alignment */
align-items: baseline;
align-items: first baseline;
align-items: last baseline; /* Overflow alignment (for positional alignment only) */
align-items: safe center;
align-items: unsafe center;

/* Global values */
align-items: inherit;
align-items: initial;
align-items: revert;
align-items: revert-layer;
align-items: unset;
```

### Values

[`normal`](#normal)

:   The effect of this keyword is dependent of the layout mode we are
    in:

    -   In absolutely-positioned layouts, the keyword behaves like
        `start` on *replaced* absolutely-positioned boxes, and as
        `stretch` on *all other* absolutely-positioned boxes.
    -   In static position of absolutely-positioned layouts, the keyword
        behaves as `stretch`.
    -   For flex items, the keyword behaves as `stretch`.
    -   For grid items, this keyword leads to a behavior similar to the
        one of `stretch`, except for boxes with an aspect ratio or an
        intrinsic sizes where it behaves like `start`.
    -   The property doesn\'t apply to block-level boxes, and to table
        cells.

[`flex-start`](#flex-start)

:   Used in flex layout only, aligns the flex items flush against the
    flex container\'s main-start or cross-start side.

[`flex-end`](#flex-end)

:   Used in flex layout only, aligns the flex items flush against the
    flex container\'s main-end or cross-end side.

[`center`](#center)

:   The flex items\' margin boxes are centered within the line on the
    cross-axis. If the cross-size of an item is larger than the flex
    container, it will overflow equally in both directions.

[`start`](#start)

:   The items are packed flush to each other toward the start edge of
    the alignment container in the appropriate axis.

[`end`](#end)

:   The items are packed flush to each other toward the end edge of the
    alignment container in the appropriate axis.

[`self-start`](#self-start)

:   The items are packed flush to the edge of the alignment container\'s
    start side of the item, in the appropriate axis.

[`self-end`](#self-end)

:   The items are packed flush to the edge of the alignment container\'s
    end side of the item, in the appropriate axis.

[`baseline`](#baseline), `first baseline`, `last baseline`

:   All flex items are aligned such that their [flex container
    baselines](https://drafts.csswg.org/css-flexbox-1/#flex-baselines)
    align. The item with the largest distance between its cross-start
    margin edge and its baseline is flushed with the cross-start edge of
    the line.

[`stretch`](#stretch)

:   If the items are smaller than the alignment container, auto-sized
    items will be equally enlarged to fill the container, respecting the
    items\' width and height limits.

[`safe`](#safe)

:   Used alongside an alignment keyword. If the chosen keyword means
    that the item overflows the alignment container causing data loss,
    the item is instead aligned as if the alignment mode were `start`.

[`unsafe`](#unsafe)

:   Used alongside an alignment keyword. Regardless of the relative
    sizes of the item and alignment container and whether overflow which
    causes data loss might happen, the given alignment value is honored.

Formal definition
-----------------

  ---------------------------------- --------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- --------------

Formal syntax
-------------

```
align-items = 
  normal                                    |
  stretch                                   |
  <baseline-position>                       |
  [ <overflow-position>? <self-position> ]  

<baseline-position> = 
  [ first | last ]?  &&
  baseline           

<overflow-position> = 
  unsafe  |
  safe    

<self-position> = 
  center      |
  start       |
  end         |
  self-start  |
  self-end    |
  flex-start  |
  flex-end    
```

Examples
--------

### CSS

[css]

```css
#container {
  height: 200px;
  width: 240px;
  align-items: center; /* Can be changed in the live sample */
  background-color: #8c8c8c;
}

.flex {
  display: flex;
  flex-wrap: wrap;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, 50px);
}

div > div {
  box-sizing: border-box;
  border: 2px solid #8c8c8c;
  width: 50px;
  display: flex;
  align-items: center;
  justify-content: center;
}

#item1 {
  background-color: #8cffa0;
  min-height: 30px;
}

#item2 {
  background-color: #a0c8ff;
  min-height: 50px;
}

#item3 {
  background-color: #ffa08c;
  min-height: 40px;
}

#item4 {
  background-color: #ffff8c;
  min-height: 60px;
}

#item5 {
  background-color: #ff8cff;
  min-height: 70px;
}

#item6 {
  background-color: #8cffff;
  min-height: 50px;
  font-size: 30px;
}

select {
  font-size: 16px;
}

.row {
  margin-top: 10px;
}
```

### HTML

[html]

```html
<div id="container" class="flex">
  <div id="item1">1</div>
  <div id="item2">2</div>
  <div id="item3">3</div>
  <div id="item4">4</div>
  <div id="item5">5</div>
  <div id="item6">6</div>
</div>

<div class="row">
  <label for="display">display: </label>
  <select id="display">
    <option value="flex">flex</option>
    <option value="grid">grid</option>
  </select>
</div>

<div class="row">
  <label for="values">align-items: </label>
  <select id="values">
    <option value="normal">normal</option>
    <option value="flex-start">flex-start</option>
    <option value="flex-end">flex-end</option>
    <option value="center" selected>center</option>
    <option value="baseline">baseline</option>
    <option value="stretch">stretch</option>

    <option value="start">start</option>
    <option value="end">end</option>
    <option value="self-start">self-start</option>
    <option value="self-end">self-end</option>

    <option value="first baseline">first baseline</option>
    <option value="last baseline">last baseline</option>

    <option value="safe center">safe center</option>
    <option value="unsafe center">unsafe center</option>
    <option value="safe right">safe right</option>
    <option value="unsafe right">unsafe right</option>
    <option value="safe end">safe end</option>
    <option value="unsafe end">unsafe end</option>
    <option value="safe self-end">safe self-end</option>
    <option value="unsafe self-end">unsafe self-end</option>
    <option value="safe flex-end">safe flex-end</option>
    <option value="unsafe flex-end">unsafe flex-end</option>
  </select>
</div>
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\# align-items-property]](https://drafts.csswg.org/css-align/#align-items-property)

[CSS Flexible Box Layout Module Level 1\
  [\#
  align-items-property]](https://drafts.csswg.org/css-flexbox/#align-items-property)
  --------------------------------------------------------------------------------------------

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

`align-items`

2921

1212

4920

11

1615

97

4.44.4

2925

4920

1614

97

2.01.5

`flex_context`

52

21--52Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Chrome implements the new behavior
beginning with Chrome 52.

12

20Multi-line flexbox has been supported since Firefox 28.

11In Internet Explorer 10 and 11, if column flex items have
`align-items: center;` set on them and their content is too large, then
they will overflow the bounds of their container. See [Flexbug
\#2](https://github.com/philipwalton/flexbugs#2-column-flex-items-set-to-align-itemscenter-overflow-their-container).

39

15--39Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Opera implements the new behavior
beginning with Opera 39.

7

52

4.4--52Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Chrome implements the new behavior
beginning with Chrome 52.

52

25--52Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Chrome implements the new behavior
beginning with Chrome 52.

20Multi-line flexbox has been supported since Firefox 28.

41

14--41Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Opera implements the new behavior
beginning with Opera 41.

7

6.0

1.5--6.0Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Samsung Internet implements the new
behavior beginning with Samsung Internet 6.0.

`grid_context`

57

16

52

No

44

10.1

57

52

52

43

10.3

6.2

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](aligning_items_in_a_flex_container.md)*
- CSS Grid Guide: *[](_Resources/Markup%20And%20Styling/css/css_grid_layout/box_alignment_in_grid_layout.md)*
- [CSS Box Alignment](css_box_alignment.md)
- The [`align-self`](align-self.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/align-items>

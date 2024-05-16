align-content
=============

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
`align-content` property sets the distribution of space between and
around content items along a [flexbox](css_flexible_box_layout.md)\'s
cross-axis or a [grid](css_grid_layout.md)\'s block axis.

The interactive example below uses Grid Layout to demonstrate some of
the values of this property.

Try it
------

This property has no effect on single line flex containers (i.e. ones
with `flex-wrap: nowrap`).

Syntax
------

[css]

```css
/* Basic positional alignment */
/* align-content does not take left and right values */
align-content: center; /* Pack items around the center */
align-content: start; /* Pack items from the start */
align-content: end; /* Pack items from the end */
align-content: flex-start; /* Pack flex items from the start */
align-content: flex-end; /* Pack flex items from the end */

/* Normal alignment */
align-content: normal;

/* Baseline alignment */
align-content: baseline;
align-content: first baseline;
align-content: last baseline;

/* Distributed alignment */
align-content: space-between; /* Distribute items evenly
                                 The first item is flush with the start,
                                 the last is flush with the end */
align-content: space-around; /* Distribute items evenly
                                 Items have a half-size space
                                 on either end */
align-content: space-evenly; /* Distribute items evenly
                                 Items have equal space around them */
align-content: stretch; /* Distribute items evenly
                                 Stretch 'auto'-sized items to fit
                                 the container */

/* Overflow alignment */
align-content: safe center;
align-content: unsafe center;

/* Global values */
align-content: inherit;
align-content: initial;
align-content: revert;
align-content: revert-layer;
align-content: unset;
```

### Values

[`start`](#start)

:   The items are packed flush to each other against the start edge of
    the alignment container in the cross axis.

[`end`](#end)

:   The items are packed flush to each other against the end edge of the
    alignment container in the cross axis.

[`flex-start`](#flex-start)

:   The items are packed flush to each other against the edge of the
    alignment container depending on the flex container\'s cross-start
    side. This only applies to flex layout items. For items that are not
    children of a flex container, this value is treated like `start`.

[`flex-end`](#flex-end)

:   The items are packed flush to each other against the edge of the
    alignment container depending on the flex container\'s cross-end
    side. This only applies to flex layout items. For items that are not
    children of a flex container, this value is treated like `end`.

[`center`](#center)

:   The items are packed flush to each other in the center of the
    alignment container along the cross axis.

[`normal`](#normal)

:   The items are packed in their default position as if no
    `align-content` value was set.

[`baseline`](#baseline), `first baseline`, `last baseline`

:   Specifies participation in first- or last-baseline alignment: aligns
    the alignment baseline of the box\'s first or last baseline set with
    the corresponding baseline in the shared first or last baseline set
    of all the boxes in its baseline-sharing group.

    ![the baseline is the line upon which most letters \"sit\" and below
    which descenders extend.](data:image/png;base64,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)

    The fallback alignment for `first baseline` is `start`, the one for
    `last baseline` is `end`.

[`space-between`](#space-between)

:   The items are evenly distributed within the alignment container
    along the cross axis. The spacing between each pair of adjacent
    items is the same. The first item is flush with the start edge of
    the alignment container in the cross axis, and the last item is
    flush with the end edge of the alignment container in the cross
    axis.

[`space-around`](#space-around)

:   The items are evenly distributed within the alignment container
    along the cross axis. The spacing between each pair of adjacent
    items is the same. The empty space before the first and after the
    last item equals half of the space between each pair of adjacent
    items.

[`space-evenly`](#space-evenly)

:   The items are evenly distributed within the alignment container
    along the cross axis. The spacing between each pair of adjacent
    items, the start edge and the first item, and the end edge and the
    last item, are all exactly the same.

[`stretch`](#stretch)

:   If the combined size of the items along the cross axis is less than
    the size of the alignment container, any `auto`-sized items have
    their size increased equally (not proportionally), while still
    respecting the constraints imposed by
    [`max-height`](max-height.md)/[`max-width`](max-width.md) (or equivalent
    functionality), so that the combined size exactly fills the
    alignment container along the cross axis.

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

  ---------------------------------- ----------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         multi-line flex containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ----------------------------

Formal syntax
-------------

```
align-content = 
  normal                                   |
  <baseline-position>                      |
  <content-distribution>                   |
  <overflow-position>? <content-position>  

<baseline-position> = 
  [ first | last ]?  &&
  baseline           

<content-distribution> = 
  space-between  |
  space-around   |
  space-evenly   |
  stretch        

<overflow-position> = 
  unsafe  |
  safe    

<content-position> = 
  center      |
  start       |
  end         |
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
  align-content: center; /* Can be changed in the live sample */
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
  <label for="values">align-content: </label>
  <select id="values">
    <option value="normal">normal</option>
    <option value="stretch">stretch</option>
    <option value="flex-start">flex-start</option>
    <option value="flex-end">flex-end</option>
    <option value="center" selected>center</option>
    <option value="space-between">space-between</option>
    <option value="space-around">space-around</option>
    <option value="space-evenly">space-evenly</option>

    <option value="start">start</option>
    <option value="end">end</option>

    <option value="baseline">baseline</option>
    <option value="first baseline">first baseline</option>
    <option value="last baseline">last baseline</option>

    <option value="safe center">safe center</option>
    <option value="unsafe center">unsafe center</option>
    <option value="safe right">safe right</option>
    <option value="unsafe right">unsafe right</option>
    <option value="safe end">safe end</option>
    <option value="unsafe end">unsafe end</option>
    <option value="safe flex-end">safe flex-end</option>
    <option value="unsafe flex-end">unsafe flex-end</option>
  </select>
</div>
```

### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\# align-justify-content]](https://drafts.csswg.org/css-align/#align-justify-content)

[CSS Flexible Box Layout Module Level 1\
  [\#
  align-content-property]](https://drafts.csswg.org/css-flexbox/#align-content-property)
  ------------------------------------------------------------------------------------------------

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

`align-content`

2921

1212

4928

11

1615

97

≤374.4

2925

4928

1614

97

2.01.5

`flex_context`

21

12

28

11

15

9

4.4

25

28

14

9

1.5

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/align-content>

align-self
==========

The `align-self` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property overrides a grid or flex item\'s [`align-items`](align-items.md)
value. In Grid, it aligns the item inside the [grid
area](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Areas). In
Flexbox, it aligns the item on the [cross
axis](https://developer.mozilla.org/en-US/docs/Glossary/Cross_Axis).

Try it
------

The property doesn\'t apply to block-level boxes, or to table cells. If
a flexbox item\'s cross-axis margin is `auto`, then `align-self` is
ignored.

Syntax
------

[css]

```css
/* Keyword values */
align-self: auto;
align-self: normal;

/* Positional alignment */
/* align-self does not take left and right values */
align-self: center; /* Put the item around the center */
align-self: start; /* Put the item at the start */
align-self: end; /* Put the item at the end */
align-self: self-start; /* Align the item flush at the start */
align-self: self-end; /* Align the item flush at the end */
align-self: flex-start; /* Put the flex item at the start */
align-self: flex-end; /* Put the flex item at the end */

/* Baseline alignment */
align-self: baseline;
align-self: first baseline;
align-self: last baseline;
align-self: stretch; /* Stretch 'auto'-sized items to fit the container */

/* Overflow alignment */
align-self: safe center;
align-self: unsafe center;

/* Global values */
align-self: inherit;
align-self: initial;
align-self: revert;
align-self: revert-layer;
align-self: unset;
```

### Values

[`auto`](#auto)

:   Computes to the parent\'s [`align-items`](align-items.md) value.

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

[`self-start`](#self-start)

:   Aligns the items to be flush with the edge of the alignment
    container corresponding to the item\'s start side in the cross axis.

[`self-end`](#self-end)

:   Aligns the items to be flush with the edge of the alignment
    container corresponding to the item\'s end side in the cross axis.

[`flex-start`](#flex-start)

:   The cross-start margin edge of the flex item is flushed with the
    cross-start edge of the line.

[`flex-end`](#flex-end)

:   The cross-end margin edge of the flex item is flushed with the
    cross-end edge of the line.

[`center`](#center)

:   The flex item\'s margin box is centered within the line on the
    cross-axis. If the cross-size of the item is larger than the flex
    container, it will overflow equally in both directions.

[`baseline`](#baseline), `first baseline`, `last baseline`

:   Specifies participation in first- or last-baseline alignment: aligns
    the alignment baseline of the box\'s first or last baseline set with
    the corresponding baseline in the shared first or last baseline set
    of all the boxes in its baseline-sharing group. The fallback
    alignment for `first baseline` is `start`, the one for
    `last baseline` is `end`.

[`stretch`](#stretch)

:   If the combined size of the items along the cross axis is less than
    the size of the alignment container and the item is `auto`-sized,
    its size is increased equally (not proportionally), while still
    respecting the constraints imposed by
    [`max-height`](max-height.md)/[`max-width`](max-width.md) (or equivalent
    functionality), so that the combined size of all `auto`-sized items
    exactly fills the alignment container along the cross axis.

[`safe`](#safe)

:   If the size of the item overflows the alignment container, the item
    is instead aligned as if the alignment mode were `start`.

[`unsafe`](#unsafe)

:   Regardless of the relative sizes of the item and alignment
    container, the given alignment value is honored.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         flex items, grid items, and absolutely-positioned boxes
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   `auto` computes to itself on absolutely-positioned elements, and to the computed value of [`align-items`](align-items.md) on the parent (minus any legacy keywords) on all other boxes, or `start` if the box has no parent. Its behavior depends on the layout model, as described for [`justify-self`](justify-self.md). Otherwise the specified value.
  Animation type                     discrete
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
align-self = 
  auto                                  |
  normal                                |
  stretch                               |
  <baseline-position>                   |
  <overflow-position>? <self-position>  

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

### HTML

[html]

```html
<section>
  <div>Item #1</div>
  <div>Item #2</div>
  <div>Item #3</div>
</section>
```

### CSS

[css]

```css
section {
  display: flex;
  align-items: center;
  height: 120px;
  background: beige;
}

div {
  height: 60px;
  background: cyan;
  margin: 5px;
}

div:nth-child(3) {
  align-self: flex-end;
  background: pink;
}
```

### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\# align-self-property]](https://drafts.csswg.org/css-align/#align-self-property)

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

`align-self`

2921

1212

4920

10

12.1

97

4.44.4

2925

4920

12.1

97

2.01.5

`flex_context`

36

21--36Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Chrome implements the new behavior
beginning with Chrome 52.

12

20Before Firefox 27, only single-line flexbox is supported.

11

12.1

7

37

4.4--37Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Chrome implements the new behavior
beginning with Chrome 52.

36

25--36Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Chrome implements the new behavior
beginning with Chrome 52.

20Before Firefox 27, only single-line flexbox is supported.

12.1

7

3.0

1.5--3.0Older versions of the specification treat absolute positioned
children as though they are a 0 by 0 flex item. Later specification
versions take the children out of the flow and set their positions based
on align and justify properties. Samsung Internet implements the new
behavior beginning with Samsung Internet 6.0.

`grid_context`

57

16

52

10Internet Explorer 10 and 11 have the property `-ms-grid-row-align`,
which acts in a similar way to `align-self`.

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
- The [`align-items`](align-items.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/align-self>

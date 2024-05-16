justify-content
===============

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
`justify-content` property defines how the browser distributes space
between and around content items along the
[main-axis](https://developer.mozilla.org/en-US/docs/Glossary/Main_Axis)
of a flex container, and the inline axis of a grid container.

The interactive example below demonstrates some of the values using Grid
Layout.

Try it
------

The alignment is done after the lengths and auto margins are applied,
meaning that, if in a [Flexbox layout](css_flexible_box_layout.md) there is
at least one flexible element, with [`flex-grow`](flex-grow.md) different
from `0`, it will have no effect as there won\'t be any available space.

Syntax
------

[css]

```css
/* Positional alignment */
justify-content: center; /* Pack items around the center */
justify-content: start; /* Pack items from the start */
justify-content: end; /* Pack items from the end */
justify-content: flex-start; /* Pack flex items from the start */
justify-content: flex-end; /* Pack flex items from the end */
justify-content: left; /* Pack items from the left */
justify-content: right; /* Pack items from the right */

/* Baseline alignment */
/* justify-content does not take baseline values */

/* Normal alignment */
justify-content: normal;

/* Distributed alignment */
justify-content: space-between; /* Distribute items evenly
                                   The first item is flush with the start,
                                   the last is flush with the end */
justify-content: space-around; /* Distribute items evenly
                                   Start and end gaps are half the size of the space
                                   between each item */
justify-content: space-evenly; /* Distribute items evenly
                                   Start, in-between, and end gaps have equal sizes */
justify-content: stretch; /* Distribute items evenly
                                   Stretch 'auto'-sized items to fit
                                   the container */

/* Overflow alignment */
justify-content: safe center;
justify-content: unsafe center;

/* Global values */
justify-content: inherit;
justify-content: initial;
justify-content: revert;
justify-content: revert-layer;
justify-content: unset;
```

### Values

[`start`](#start)

:   The items are packed flush to each other toward the start edge of
    the alignment container in the main axis.

[`end`](#end)

:   The items are packed flush to each other toward the end edge of the
    alignment container in the main axis.

[`flex-start`](#flex-start)

:   The items are packed flush to each other toward the edge of the
    alignment container depending on the flex container\'s main-start
    side. This only applies to flex layout items. For items that are not
    children of a flex container, this value is treated like `start`.

[`flex-end`](#flex-end)

:   The items are packed flush to each other toward the edge of the
    alignment container depending on the flex container\'s main-end
    side. This only applies to flex layout items. For items that are not
    children of a flex container, this value is treated like `end`.

[`center`](#center)

:   The items are packed flush to each other toward the center of the
    alignment container along the main axis.

[`left`](#left)

:   The items are packed flush with each other toward the left edge of
    the alignment container. When the property\'s horizontal axis is not
    parallel with the inline axis, such as when
    [`flex-direction: column;`](flex-direction.md) is set, this value
    behaves like `start`.

[`right`](#right)

:   The items are packed flush to each other toward the right edge of
    the alignment container in the appropriate axis. If the property\'s
    axis is not parallel with the inline axis (in a grid container) or
    the main-axis (in a flexbox container), this value behaves like
    `start`.

[`normal`](#normal)

:   Behaves as `stretch`, except in the case of multi-column containers
    with a non-`auto` [`column-width`](column-width.md), in which case the
    columns take their specified `column-width` rather than stretching
    to fill the container. As `stretch` behaves as `start` in flex
    containers, `normal` also behaves as `start`.

[`space-between`](#space-between)

:   The items are evenly distributed within the alignment container
    along the main axis. The spacing between each pair of adjacent items
    is the same. The first item is flush with the main-start edge, and
    the last item is flush with the main-end edge.

[`space-around`](#space-around)

:   The items are evenly distributed within the alignment container
    along the main axis. The spacing between each pair of adjacent items
    is the same. The empty space before the first and after the last
    item equals half of the space between each pair of adjacent items.

[`space-evenly`](#space-evenly)

:   The items are evenly distributed within the alignment container
    along the main axis. The spacing between each pair of adjacent
    items, the main-start edge and the first item, and the main-end edge
    and the last item, are all exactly the same.

[`stretch`](#stretch)

:   If the combined size of the items along the main axis is less than
    the size of the alignment container, any `auto`-sized items have
    their size increased equally (not proportionally), while still
    respecting the constraints imposed by
    [`max-height`](max-height.md)/[`max-width`](max-width.md) (or equivalent
    functionality), so that the combined size exactly fills the
    alignment container along the main axis.

    **Note:** While `stretch` is supported by flexible boxes (flexbox),
    when applied on a flexbox, as stretching is controlled by
    [`flex`](flex), `stretch` behaves as `start`.

[`safe`](#safe)

:   If the item overflows the alignment container, then the item is
    aligned as if the alignment mode is `start`. The desired alignment
    will not be implemented.

[`unsafe`](#unsafe)

:   Even if the item overflows the alignment container, the desired
    alignment will be implemented. Unlike `safe`, which will ignore the
    desired alignment in favor of preventing overflow.

Formal definition
-----------------

  ---------------------------------- -----------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         flex containers
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -----------------

Formal syntax
-------------

```
justify-content = 
  normal                                              |
  <content-distribution>                              |
  <overflow-position>? [ <content-position> | left | right ]  

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

### Setting flex item distribution

#### CSS

[css]

```css
#container {
  display: flex;
  justify-content: space-between; /* Can be changed in the live sample */
}

#container > div {
  width: 100px;
  height: 100px;
  background: linear-gradient(-45deg, #788cff, #b4c8ff);
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\# align-justify-content]](https://drafts.csswg.org/css-align/#align-justify-content)

[CSS Flexible Box Layout Module Level 1\
  [\#
  justify-content-property]](https://drafts.csswg.org/css-flexbox/#justify-content-property)
  ----------------------------------------------------------------------------------------------------

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

`justify-content`

2921

1212

4920

11

12.1

97

4.44.4

2925

4920

12.1

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

20Before Firefox 27, Firefox supported only single-line flexbox.

11

12.1

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

20Before Firefox 27, Firefox supported only single-line flexbox.

12.1

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

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/justify-content>

align-tracks
============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `align-tracks` CSS property sets the alignment in the masonry axis
for grid containers that have [masonry](masonry_layout.md)
in their block axis.

Syntax
------

[css]

```css
/* Keyword values */
align-tracks: start;
align-tracks: space-between;
align-tracks: center;
align-tracks: start, center, end;

/* Global values */
align-tracks: inherit;
align-tracks: initial;
align-tracks: revert;
align-tracks: revert-layer;
align-tracks: unset;
```

The property can take a single value, in which case all tracks are
aligned in the same way. If a list of values is used then the first
value applies to the first track in the grid axis, the second to the
next and so on.

If there are fewer values than tracks, the last value is used for all
remaining tracks. If there are more values than tracks, any additional
values are ignored.

### Values

[`start`](#start)

:   The items are packed flush to each other toward the start edge of
    the alignment container in the masonry axis.

[`end`](#end)

:   The items are packed flush to each other toward the end edge of the
    alignment container in the masonry axis.

[`center`](#center)

:   The items are packed flush to each other toward the center of the
    alignment container along the masonry axis.

[`normal`](#normal)

:   Acts as `start`.

[`baseline first baseline`](#sect2) `last baseline`

:   Specifies participation in first- or last-baseline alignment: aligns
    the alignment baseline of the box\'s first or last baseline set with
    the corresponding baseline in the shared first or last baseline set
    of all the boxes in its baseline-sharing group. The fallback
    alignment for `first baseline` is `start`, the one for
    `last baseline` is `end`.

[`space-between`](#space-between)

:   The items are evenly distributed within the alignment container
    along the masonry axis. The spacing between each pair of adjacent
    items is the same. The first item is flush with the main-start edge,
    and the last item is flush with the main-end edge.

[`space-around`](#space-around)

:   The items are evenly distributed within the alignment container
    along the masonry axis. The spacing between each pair of adjacent
    items is the same. The empty space before the first and after the
    last item equals half of the space between each pair of adjacent
    items.

[`space-evenly`](#space-evenly)

:   The items are evenly distributed within the alignment container
    along the masonry axis. The spacing between each pair of adjacent
    items, the main-start edge and the first item, and the main-end edge
    and the last item, are all exactly the same.

[`stretch`](#stretch)

:   The items stretch along the masonry axis to fill the content box.
    Items with definite size do not stretch.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         Grid containers with masonry layout in their block axis
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------------------------------------------------

Formal syntax
-------------

```
align-tracks = 
  [ normal | <baseline-position> | <content-distribution> | <overflow-position>? <content-position> ]#  

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

### Masonry layout with multiple values for align-tracks

Specifications
--------------

  -----------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 3\
  [\#
  tracks-alignment]](https://drafts.csswg.org/css-grid-3/#tracks-alignment)

  -----------------------------------------------------------------------------------

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

`align-tracks`

No

No

77

No

No

No

No

No

No

No

No

No

See also
--------

- Related CSS properties: [`justify-tracks`](justify-tracks.md),
    [`masonry-auto-flow`](masonry-auto-flow.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/align-tracks>

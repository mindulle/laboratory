Masonry layout
==============

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

Level 3 of the [CSS grid layout](css_grid_layout.md) specification
includes a `masonry` value for
[`grid-template-columns`](grid-template-columns.md) and
[`grid-template-rows`](grid-template-rows.md). This guide details what
masonry layout is and how to use it.

Masonry layout is a layout method where one axis uses a typical strict
grid layout, most often columns, and the other a masonry layout. On the
masonry axis, rather than sticking to a strict grid with gaps being left
after shorter items, the items in the following row rise up to
completely fill the gaps.

Creating a masonry layout
-------------------------

To create the most common masonry layout, your columns will be the grid
axis and the rows the masonry axis. Define this layout with
`grid-template-columns` and `grid-template-rows`:

[css]

```css
.container {
  display: grid;
  gap: 10px;
  grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
  grid-template-rows: masonry;
}
```

The child elements of this container will now lay out item by item along
the rows, as they would with regular grid layout automatic placement.
However, as they move onto a new row the items will display according to
the masonry algorithm. Items will load into the column with the most
room causing a tightly packed layout without strict row tracks.

It is also possible to create a masonry layout with items loading into
rows.

Controlling the grid axis
-------------------------

On the grid axis, things will work just as you expect them to in grid
layout. You can cause items to span multiple tracks while remaining in
auto-placement, using the `span` keyword. Items may also be positioned
using line-based positioning.

### Masonry layout with spanning items

In this example two of the items span two tracks, and the masonry items
work around them.

This example includes an item which has positioning for columns. Items
with definite placement are placed before the masonry layout happens.

Controlling the masonry axis
----------------------------

The masonry axis operates under different rules as it is following the
masonry layout rules rather than normal grid auto-placement rules. To
control this axis we have three additional properties defined in the
Grid Level 3 specification [`align-tracks`](align-tracks.md),
[`justify-tracks`](justify-tracks.md), and
[`masonry-auto-flow`](masonry-auto-flow.md).

### masonry-auto-flow

The `masonry-auto-flow` property gives you a way to change how the
masonry algorithm behaves. Give it a value of `next` and items will
display in order on the grid axis, rather than going into whichever
track has the most free space. The value `positioned` will ignore items
with definite placement and place items in order-modified document
order.

### align-tracks

The `align-tracks` property allows for the alignment of items in grid
containers with masonry in their block axis. The property aligns the
items within their track, much in the way flex layout works. The
property takes the same values as `align-content`, however you can
specify multiple values to have different alignment values per track on
the grid axis.

If you specify more values than tracks the additional values are
ignored. If there are more tracks than values any additional tracks will
use the last specified value.

### justify-tracks

The `justify-tracks` property works in the same way as align-tracks,
however it is used when the masonry axis is the inline axis.

Fallback
--------

In browsers [that do not support masonry](#browser_compatibility),
regular grid auto-placement will be used instead.

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

`Masonry_layout`

No

No

77

No

No

preview

No

No

No

No

No

No

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

`Masonry_layout`

No

No

77

No

No

preview

No

No

No

No

No

No

### css.properties.grid-template-columns.masonry

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.grid-template-rows.masonry

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- [Native CSS Masonry Layout In CSS
    Grid](https://www.smashingmagazine.com/native-css-masonry-layout-css-grid/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_grid_layout/Masonry_layout>

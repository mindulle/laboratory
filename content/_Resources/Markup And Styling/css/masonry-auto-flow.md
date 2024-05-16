masonry-auto-flow
=================

**Experimental:** **This is an [experimental
technology](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Experimental_deprecated_obsolete#experimental)**\
Check the [Browser compatibility table](#browser_compatibility)
carefully before using this in production.

The `masonry-auto-flow` CSS property modifies how items are placed when
using [masonry](masonry_layout.md) in [](css_grid_layout.md).

Syntax
------

[css]

```css
/* Keyword values */
masonry-auto-flow: pack;
masonry-auto-flow: next;
masonry-auto-flow: ordered;
masonry-auto-flow: definite-first;
masonry-auto-flow: next ordered;

/* Global values */
masonry-auto-flow: inherit;
masonry-auto-flow: initial;
masonry-auto-flow: revert;
masonry-auto-flow: revert-layer;
masonry-auto-flow: unset;
```

This property may take one of two forms:

- A single keyword: one of `pack`, `next`, `definite-first`, or
    `ordered`
- Two keywords, for example `next ordered`.

### Values

[`pack`](#pack)

:   As per the default masonry algorithm, items will be placed into the
    track with the most room.

[`next`](#next)

:   Items will be placed one after the other in the grid axis.

[`definite-first`](#definite-first)

:   Display as in the default masonry algorithm, placing items with a
    definite place first before placing other masonry items.

[`ordered`](#ordered)

:   Ignore any items with a definite placement, and place everything
    according to order-modified document order.

Formal definition
-----------------

  ---------------------------------- -------------------------------------
  [Initial value](initial_value.md)     `pack`
  Applies to                         Grid containers with masonry layout
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- -------------------------------------

Formal syntax
-------------

```
masonry-auto-flow = 
  [ pack | next ]               ||
  [ definite-first | ordered ]  
```

Examples
--------

### Using the next keyword

#### HTML

[html]

```html
<div id="grid">
  <div id="item1"></div>
  <div id="item2"></div>
  <div id="item3"></div>
  <div id="item4"></div>
  <div id="item5"></div>
</div>
<select id="flow">
  <option value="pack">pack</option>
  <option value="next">next</option>
</select>
```

#### CSS

[css]

```css
#grid {
  height: 200px;
  width: 200px;
  display: grid;
  gap: 10px;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: masonry;
  masonry-auto-flow: pack;
}

#item1 {
  background-color: lime;
  height: 2em;
}

#item2 {
  background-color: yellow;
}

#item3 {
  background-color: blue;
  height: 3em;
}

#item4 {
  background-color: red;
  height: 2.5em;
}

#item5 {
  background-color: aqua;
  height: 4em;
}
```

[js]

```js
const selectElem = document.querySelector("select");

function changeMasonryFlow() {
  const grid = document.getElementById("grid");
  const direction = document.getElementById("flow");
  const masonryAutoFlow = direction.value === "pack" ? "pack" : "next";

  grid.style.masonryAutoFlow = masonryAutoFlow;
}

selectElem.addEventListener("change", changeMasonryFlow);
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 3\
  [\#
  masonry-auto-flow]](https://drafts.csswg.org/css-grid-3/#masonry-auto-flow)

  -------------------------------------------------------------------------------------

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

`masonry-auto-flow`

No

No

No

No

No

preview

No

No

No

No

No

No

See also
--------

- Related CSS properties: [`align-tracks`](align-tracks.md),
    [`justify-tracks`](justify-tracks.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/masonry-auto-flow>

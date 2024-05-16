minmax()
========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `minmax()` [CSS function](css_functions.md) defines a size range
greater than or equal to *min* and less than or equal to *max*. It is
used with [CSS Grids](css_grid_layout.md).

Try it
------

Syntax
------

[css]

```css
/* <inflexible-breadth>, <track-breadth> values */
minmax(200px, 1fr)
minmax(400px, 50%)
minmax(30%, 300px)
minmax(100px, max-content)
minmax(min-content, 400px)
minmax(max-content, auto)
minmax(auto, 300px)
minmax(min-content, auto)

/* <fixed-breadth>, <track-breadth> values */
minmax(200px, 1fr)
minmax(30%, 300px)
minmax(400px, 50%)
minmax(50%, min-content)
minmax(300px, max-content)
minmax(200px, auto)

/* <inflexible-breadth>, <fixed-breadth> values */
minmax(400px, 50%)
minmax(30%, 300px)
minmax(min-content, 200px)
minmax(max-content, 200px)
minmax(auto, 300px)
```

A function taking two parameters, *min* and *max*.

Each parameter can be a `<length>`, a `<percentage>`, a `<flex>` value,
or one of the keyword values `max-content`, `min-content`, or `auto`.

If *max* \< *min*, then *max* is ignored and `minmax(min,max)` is
treated as *min*. As a maximum, a [`<flex>`](flex_value.md) value sets the
flex factor of a grid track; it is invalid as a minimum.

### Values

[`<length>`](length.md)

:   A non-negative length.

[`<percentage>`](percentage.md)

:   A non-negative percentage relative to the inline size of the grid
    container in column grid tracks, and the block size of the grid
    container in row grid tracks. If the size of the grid container
    depends on the size of its tracks, then the `<percentage>` must be
    treated as `auto`. The [user
    agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)
    may adjust the intrinsic size contributions of the track to the size
    of the grid container and increase the final size of the track by
    the minimum amount that would result in honoring the percentage.

[`<flex>`](flex_value.md)

:   A non-negative dimension with the unit `fr` specifying the track\'s
    flex factor. Each `<flex>`-sized track takes a share of the
    remaining space in proportion to its flex factor.

[`max-content`](#max-content)

:   Represents the largest max-content contribution of the grid items
    occupying the grid track.

[`min-content`](#min-content)

:   Represents the largest min-content contribution of the grid items
    occupying the grid track.

[`auto`](#auto)

:   As `min`, it represents the largest minimum size (as specified by
    [`min-width`](min-width.md)/[`min-height`](min-height.md)) of the grid
    items occupying the grid track. As `max`, it is identical to
    `max-content`. However, unlike `max-content`, it allows expansion of
    the track by the [`align-content`](align-content.md) and
    [`justify-content`](justify-content.md) property values like `normal`
    and `stretch`.

### Formal syntax

Error: could not find syntax for this item

### CSS properties

`minmax()` function can be used within:

- [`grid-template-columns`](grid-template-columns.md)
- [`grid-template-rows`](grid-template-rows.md)
- [`grid-auto-columns`](grid-auto-columns.md)
- [`grid-auto-rows`](grid-auto-rows.md)

Examples
--------

### CSS

[css]

```css
#container {
  display: grid;
  grid-template-columns: minmax(min-content, 300px) minmax(200px, 1fr) 150px;
  grid-gap: 5px;
  box-sizing: border-box;
  height: 200px;
  width: 100%;
  background-color: #8cffa0;
  padding: 10px;
}

#container > div {
  background-color: #8ca0ff;
  padding: 5px;
}
```

### HTML

[html]

```html
<div id="container">
  <div>Item as wide as the content, but at most 300 pixels.</div>
  <div>Item with flexible width but a minimum of 200 pixels.</div>
  <div>Inflexible item of 150 pixels width.</div>
</div>
```

### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  valdef-grid-template-columns-minmax]](https://drafts.csswg.org/css-grid/#valdef-grid-template-columns-minmax)

  -----------------------------------------------------------------------------------------------------------------------

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

`minmax`

57

16

52

No

44

10.1

57

57

52

43

10.3

6.0

See also
--------

- Grid Layout Guide: *[](basic_concepts_of_grid_layout.md#track_sizing_and_minmax)*
- [](grids_logical_values_and_writing_modes.md)
- Video tutorial: *[Introducing
    minmax()](https://gridbyexample.com/video/series-minmax/)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/minmax>

grid-auto-rows
==============

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `grid-auto-rows` CSS property specifies the size of an
implicitly-created grid row
[track](https://developer.mozilla.org/en-US/docs/Glossary/Grid_Tracks)
or pattern of tracks.

Try it
------

If a grid item is positioned into a row that is not explicitly sized by
[`grid-template-rows`](grid-template-rows.md), implicit
[grid](https://developer.mozilla.org/en-US/docs/Glossary/Grid) tracks
are created to hold it. This can happen either by explicitly positioning
into a row that is out of range, or by the auto-placement algorithm
creating additional rows.

Syntax
------

[css]

```css
/* Keyword values */
grid-auto-rows: min-content;
grid-auto-rows: max-content;
grid-auto-rows: auto;

/* <length> values */
grid-auto-rows: 100px;
grid-auto-rows: 20cm;
grid-auto-rows: 50vmax;

/* <percentage> values */
grid-auto-rows: 10%;
grid-auto-rows: 33.3%;

/* <flex> values */
grid-auto-rows: 0.5fr;
grid-auto-rows: 3fr;

/* minmax() values */
grid-auto-rows: minmax(100px, auto);
grid-auto-rows: minmax(max-content, 2fr);
grid-auto-rows: minmax(20%, 80vmax);

/* fit-content() values */
grid-auto-rows: fit-content(400px);
grid-auto-rows: fit-content(5cm);
grid-auto-rows: fit-content(20%);

/* multiple track-size values */
grid-auto-rows: min-content max-content auto;
grid-auto-rows: 100px 150px 390px;
grid-auto-rows: 10% 33.3%;
grid-auto-rows: 0.5fr 3fr 1fr;
grid-auto-rows: minmax(100px, auto) minmax(max-content, 2fr) minmax(20%, 80vmax);
grid-auto-rows: 100px minmax(100px, auto) 10% 0.5fr fit-content(400px);

/* Global values */
grid-auto-rows: inherit;
grid-auto-rows: initial;
grid-auto-rows: revert;
grid-auto-rows: revert-layer;
grid-auto-rows: unset;
```

### Values

[`<length>`](length.md)

:   Is a non-negative length.

[`<percentage>`](percentage.md)

:   Is a non-negative [`<percentage>`](percentage.md) value relative to the
    block size of the grid container. If the block size of the grid
    container is indefinite, the percentage value is treated like
    `auto`.

[`<flex>`](flex_value.md)

:   Is a non-negative dimension with the unit `fr` specifying the
    track\'s flex factor. Each `<flex>`-sized track takes a share of the
    remaining space in proportion to its flex factor.

    When appearing outside a `minmax()` notation, it implies an
    automatic minimum (i.e. `minmax(auto, <flex>)`).

[`max-content`](max-content.md)

:   Is a keyword representing the largest maximal content contribution
    of the grid items occupying the grid track.

[`min-content`](min-content.md)

:   Is a keyword representing the largest minimal content contribution
    of the grid items occupying the grid track.

[`minmax(min, max)`](minmax.md)

:   Is a functional notation that defines a size range greater than or
    equal to *min* and less than or equal to *max*. If *max* is smaller
    than *min*, then *max* is ignored and the function is treated as
    *min*. As a maximum, a `<flex>` value sets the track\'s flex factor.
    As a minimum, it is treated as zero (or minimal content, if the grid
    container is sized under a minimal content constraint).

[`fit-content( [ <length> | <percentage> ] )`](fit-content_function.md)

:   Represents the formula `min(max-content, max(auto, argument))`,
    which is calculated similar to `auto` (i.e.
    `minmax(auto, max-content)`), except that the track size is clamped
    at *argument* if it is greater than the `auto` minimum.

[`auto`](#auto)

:   As a maximum represents the largest [`max-content`](max-content.md)
    size of the items in that track.

    As a minimum represents the largest minimum size of items in that
    track (specified by the
    [`min-width`](min-width)/[`min-height`](min-height) of the items).
    This is often, though not always, the [`min-content`](min-content)
    size.

    If used outside of [`minmax()`](minmax) notation, `auto` represents
    the range between the minimum and maximum described above. This
    behaves similarly to `minmax(min-content,max-content)` in most
    cases.

    
    **Note:** `auto` track sizes (and only `auto` track sizes) can be
    stretched by the [`align-content`](align-content) and
    [`justify-content`](justify-content) properties. Therefore by
    default, an `auto` sized track will take up any remaining space in
    the grid container.

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         grid containers
  [Inherited](inheritance.md)           no
  Percentages                        refer to corresponding dimension of the content area
  [Computed value](computed_value.md)   the percentage as specified or the absolute length
  Animation type                     by computed value type
  ---------------------------------- ------------------------------------------------------

Formal syntax
-------------

```
grid-auto-rows = 
  <track-size>+  

<track-size> = 
  <track-breadth>                                   |
  minmax( <inflexible-breadth> , <track-breadth> )  |
  fit-content( <length-percentage> )                

<track-breadth> = 
  <length-percentage>  |
  <flex>               |
  min-content          |
  max-content          |
  auto                 

<inflexible-breadth> = 
  <length-percentage>  |
  min-content          |
  max-content          |
  auto                 

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Setting grid row size

#### HTML

[html]

```html
<div id="grid">
  <div id="item1"></div>
  <div id="item2"></div>
  <div id="item3"></div>
</div>
```

#### CSS

[css]

```css
#grid {
  width: 200px;
  display: grid;
  grid-template-areas: "a a";
  gap: 10px;
  grid-auto-rows: 100px;
}

#grid > div {
  background-color: lime;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  auto-tracks]](https://drafts.csswg.org/css-grid/#auto-tracks)

  -----------------------------------------------------------------------

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

`grid-auto-rows`

57

1612--79

70

52--70Does not accept multiple track-size values. See [bug
1339672](https://bugzil.la/1339672).

10

44

10.1

57

57

79

52--79Does not accept multiple track-size values. See [bug
1339672](https://bugzil.la/1339672).

43

10.3

6.0

See also
--------

- Related CSS properties: [`grid-auto-columns`](grid-auto-columns.md),
    [`grid-auto-flow`](grid-auto-flow.md), [`grid`](_Resources/Markup%20And%20Styling/css/grid.md)
- Grid Layout Guide: *[](auto-placement_in_grid_layout.md#sizing_rows_in_the_implicit_grid)*
- Video tutorial: *[Introducing Grid auto-placement and
    order](https://gridbyexample.com/video/series-auto-placement-order/)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/grid-auto-rows>

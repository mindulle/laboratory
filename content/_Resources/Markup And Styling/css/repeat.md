repeat()
========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `repeat()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) represents a repeated fragment of the [](basic_concepts_of_grid_layout.md), allowing a large
number of columns or rows that exhibit a recurring pattern to be written
in a more compact form.

Try it
------

This function can be used in the CSS Grid properties
[`grid-template-columns`](grid-template-columns.md) and
[`grid-template-rows`](grid-template-rows.md).

Syntax
------

[css]

```css
/* <track-repeat> values */
repeat(4, 1fr)
repeat(4, [col-start] 250px [col-end])
repeat(4, [col-start] 60% [col-end])
repeat(4, [col-start] 1fr [col-end])
repeat(4, [col-start] min-content [col-end])
repeat(4, [col-start] max-content [col-end])
repeat(4, [col-start] auto [col-end])
repeat(4, [col-start] minmax(100px, 1fr) [col-end])
repeat(4, [col-start] fit-content(200px) [col-end])
repeat(4, 10px [col-start] 30% [col-middle] auto [col-end])
repeat(4, [col-start] min-content [col-middle] max-content [col-end])

/* <auto-repeat> values */
repeat(auto-fill, 250px)
repeat(auto-fit, 250px)
repeat(auto-fill, [col-start] 250px [col-end])
repeat(auto-fit, [col-start] 250px [col-end])
repeat(auto-fill, [col-start] minmax(100px, 1fr) [col-end])
repeat(auto-fill, 10px [col-start] 30% [col-middle] 400px [col-end])

/* <fixed-repeat> values */
repeat(4, 250px)
repeat(4, [col-start] 250px [col-end])
repeat(4, [col-start] 60% [col-end])
repeat(4, [col-start] minmax(100px, 1fr) [col-end])
repeat(4, [col-start] fit-content(200px) [col-end])
repeat(4, 10px [col-start] 30% [col-middle] 400px [col-end])
```

The `repeat()` function takes two arguments:

- **repeat count**: the first argument specifies the number of times
    that the track list should be repeated. It is specified with an
    integer value of 1 or more, or with the keyword values
    [`auto-fill`](#auto-fill) or [`auto-fit`](#auto-fit). These keyword
    values repeat the set of tracks as many times as is needed to fill
    the grid container.
- **tracks**: the second argument specifies the set of tracks that
    will be repeated. Fundamentally this consists of one or more values,
    where each value represents the size of that track. Each size is
    specified using either a [`<track-size>`](#track-size) value or a
    [`<fixed-size>`](#fixed-size) value. You can also specify one or
    more [](grid_layout_using_named_grid_lines.md) before or
    after each track, by providing [`<line-names>`](#line-names) values
    before and/or after the track size.

If you use [`auto-fill`](#auto-fill) or [`auto-fit`](#auto-fit) to set
the repeat count, you may only specify track sizes using the
[`<fixed-size>`](#fixed-size) type, not the
[`<track-size>`](#track-size) type. This give us three main syntax forms
for `repeat()`:

- `<track-repeat>`, which uses:
  - an integer to set the repeat count
  - [`<track-size>`](#track-size) values to set track sizes.
- `<auto-repeat>`, which uses
  - [`auto-fill`](#auto-fill) or [`auto-fit`](#auto-fit) to set the
        repeat count
  - [`<fixed-size>`](#fixed-size) to set track sizes.
- `<fixed-repeat>`, which uses:
  - an integer to set the repeat count
  - [`<fixed-size>`](#fixed-size) values to set track sizes.

Then if a property declaration uses `<auto-repeat>`, it is only allowed
to use `<fixed-repeat>` for any additional `repeat()` calls. For
example, this is invalid, because it combines the `<auto-repeat>` form
with the `<track-repeat>` form:

[css]

```css
.wrapper {
  grid-template-columns:
    repeat(auto-fill, 10px)
    repeat(2, minmax(min-content, max-content));
}
```

There is a fourth form, `<name-repeat>`, which is used to add line names
to subgrids. It only used with the [`subgrid`](subgrid.md)
keyword and only specifies line names, not track sizes.

### Values

[`<fixed-size>`](#fixed-size)

:   One of the following forms:

    -   a [`<length-percentage>`](length-percentage) value
    -   a [`minmax()`](minmax) function with:
        -   `min` given as a [`<length-percentage>`](length-percentage)
            value
        -   `max` given as one of a
            [`<length-percentage>`](length-percentage) value, a
            [`<flex>`](flex_value) value, or one of the following
            keywords: [`min-content`](#min-content),
            [`max-content`](#max-content), or [`auto`](#auto)
    -   a [`minmax()`](minmax) function with:
        -   `min` given as a [`<length-percentage>`](length-percentage)
            value or one of the following keywords:
            [`min-content`](#min-content),
            [`max-content`](#max-content), or [`auto`](#auto)
        -   `max` given as a [`<length-percentage>`](length-percentage)
            value.

[`<flex>`](flex_value.md)

:   A non-negative dimension with the unit `fr` specifying the track\'s
    flex factor. Each `<flex>`-sized track takes a share of the
    remaining space in proportion to its flex factor.

[`<length>`](length.md)

:   A positive integer length.

[`<line-names>`](#line-names)

:   Zero or more [`<custom-ident>`](custom-ident.md) values,
    space-separated and enclosed in square brackets, like this:
    `[first header-start]`.

[`<percentage>`](percentage.md)

:   A non-negative percentage relative to the inline size of the grid
    container in column grid tracks, and the block size of the grid
    container in row grid tracks. If the size of the grid container
    depends on the size of its tracks, then the `<percentage>` must be
    treated as `auto`. The user-agent may adjust the intrinsic size
    contributions of the track to the size of the grid container and
    increase the final size of the track by the minimum amount that
    would result in honoring the percentage.

[`<track-size>`](#track-size)

:   One of the following forms:

    -   a [`<length-percentage>`](length-percentage) value, a
        [`<flex>`](flex_value) value, or one of the following keywords:
        [`min-content`](#min-content), [`max-content`](#max-content), or
        [`auto`](#auto)
    -   a [`minmax()`](minmax) function with:
        -   `min` given as a [`<length-percentage>`](length-percentage)
            value, or one of the following keywords:
            [`min-content`](#min-content),
            [`max-content`](#max-content), or [`auto`](#auto)
        -   `max` given as a [`<length-percentage>`](length-percentage)
            value, a [`<flex>`](flex_value) value, or one of the
            following keywords: [`min-content`](#min-content),
            [`max-content`](#max-content), or [`auto`](#auto)
    -   a [`fit-content()`](fit-content_function) function, passed a
        [`<length-percentage>`](length-percentage) value.

[`auto`](#auto)

:   As a maximum, identical to `max-content`. As a minimum it represents
    the largest minimum size (as specified by
    [`min-width`](min-width.md)/[`min-height`](min-height.md)) of the grid
    items occupying the grid track.

[`auto-fill`](#auto-fill)

:   If the grid container has a definite or maximal size in the relevant
    axis, then the number of repetitions is the largest possible
    positive integer that does not cause the grid to overflow its grid
    container. Treating each track as its maximal track sizing function
    (each independent value used to define `grid-template-rows` or
    `grid-template-columns`), if that is definite. Otherwise, as its
    minimum track sizing function, and taking grid-gap into account. If
    any number of repetitions would overflow, then the repetition is
    `1`. Otherwise, if the grid container has a definite minimal size in
    the relevant axis, the number of repetitions is the smallest
    possible positive integer that fulfills that minimum requirement.
    Otherwise, the specified track list repeats only once.

[`auto-fit`](#auto-fit)

:   Behaves the same as `auto-fill`, except that after placing the grid
    items any empty repeated tracks are collapsed. An empty track is one
    with no in-flow grid items placed into or spanning across it. (This
    can result in all tracks being collapsed, if they\'re all empty.)

    A collapsed track is treated as having a single fixed track sizing
    function of `0px`, and the gutters on either side of it collapse.

    For the purpose of finding the number of auto-repeated tracks, the
    user agent floors the track size to a user agent specified value
    (e.g., `1px`), to avoid division by zero.

[`max-content`](#max-content)

:   Represents the largest max-content contribution of the grid items
    occupying the grid track.

[`min-content`](#min-content)

:   Represents the largest min-content contribution of the grid items
    occupying the grid track.

Examples
--------

### Specifying grid columns using repeat()

#### HTML

[html]

```html
<div id="container">
  <div>This item is 50 pixels wide.</div>
  <div>Item with flexible width.</div>
  <div>This item is 50 pixels wide.</div>
  <div>Item with flexible width.</div>
  <div>Inflexible item of 100 pixels width.</div>
</div>
```

#### CSS

[css]

```css
#container {
  display: grid;
  grid-template-columns: repeat(2, 50px 1fr) 100px;
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

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\#
  repeat-notation]](https://drafts.csswg.org/css-grid/#repeat-notation)

  -------------------------------------------------------------------------------

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

`repeat`

57

16

76

57--76`repeat(auto-fill, ...)` and `repeat(auto-fit, ...)` only support
one repeated column (see [bug 1341507](https://bugzil.la/1341507)).

52--57[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc)
doesn\'t work in `repeat()` (see [bug
1350069](https://bugzil.la/1350069)).

No

44

10.1

57

57

79

57--79`repeat(auto-fill, ...)` and `repeat(auto-fit, ...)` only support
one repeated column (see [bug 1341507](https://bugzil.la/1341507)).

52--57[`calc()`](https://developer.mozilla.org/docs/Web/CSS/calc)
doesn\'t work in `repeat()` (see [bug
1350069](https://bugzil.la/1350069)).

43

10.3

6.0

See also
--------

- Related CSS properties: [`grid-template`](grid-template.md),
    [`grid-template-rows`](grid-template-rows.md),
    [`grid-template-columns`](grid-template-columns.md),
    [`grid-template-areas`](grid-template-areas.md),
    [`grid-auto-columns`](grid-auto-columns.md),
    [`grid-auto-rows`](grid-auto-rows.md),
    [`grid-auto-flow`](grid-auto-flow.md)
- Grid Layout Guide: *[](grid_layout_using_line-based_placement.md)*
- Grid Layout Guide: *[](grid_template_areas.md#grid_definition_shorthands)*

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/repeat>

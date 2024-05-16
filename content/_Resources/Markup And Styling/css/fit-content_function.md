fit-content()
=============

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `fit-content()`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) clamps a given size to an available size
according to the formula
`min(maximum size, max(minimum size, argument))`.

Try it
------

The function can be used as a track size in [CSS Grid](css_grid_layout.md)
properties, where the maximum size is defined by `max-content` and the
minimum size by `auto`, which is calculated similar to `auto` (i.e.,
[`minmax(auto, max-content)`](minmax.md)), except that the track size is
clamped at *argument* if it is greater than the `auto` minimum.

See the [`grid-template-columns`](grid-template-columns.md) page for more
information on the `max-content` and `auto` keywords.

The `fit-content()` function can also be used as laid out box size for
[`width`](_Resources/Markup%20And%20Styling/css/width.md), [`height`](_Resources/Markup%20And%20Styling/css/height.md), [`min-width`](min-width.md),
[`min-height`](min-height.md), [`max-width`](max-width.md) and
[`max-height`](max-height.md), where the maximum and minimum sizes refer to
the content size.

Syntax
------

The `fit-content()` function accepts a `<length>` or a `<percentage>` as
an argument.

[css]

```css
/* <length> values */
fit-content(200px)
fit-content(5cm)
fit-content(30vw)
fit-content(100ch)

/* <percentage> value */
fit-content(40%)
```

### Values

[`<length>`](length.md)

:   An absolute length.

[`<percentage>`](percentage.md)

:   A percentage relative to the available space in the given axis.

    In grid properties it is relative to the inline size of the grid
    container in column tracks and to the block size of the grid
    container for row tracks. Otherwise it is relative to the available
    inline size or block size of the laid out box depending on the
    writing mode.

Examples
--------

### Sizing grid columns with fit-content

#### HTML

[html]

```html
<div id="container">
  <div>Item as wide as the content.</div>
  <div>
    Item with more text in it. Because the contents of it are wider than the
    maximum width, it is clamped at 300 pixels.
  </div>
  <div>Flexible item</div>
</div>
```

#### CSS

[css]

```css
#container {
  display: grid;
  grid-template-columns: fit-content(300px) fit-content(300px) 1fr;
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

  [CSS Box Sizing Module Level 4\
  [\#
  sizing-values]](https://drafts.csswg.org/css-sizing-4/#sizing-values)

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

`fit-content_function`

No

No

91

No

No

No

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

`fit-content_function`

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

### css.properties.grid-template-columns.fit-content

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

### css.properties.width.fit-content\_function

BCD tables only load in the browser with JavaScript enabled. Enable
JavaScript to view data.

See also
--------

- Related sizing keywords: [`min-content`](min-content.md),
    [`max-content`](max-content.md)
- Related CSS Grid properties: [`grid-template`](grid-template.md),
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
https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content_function>

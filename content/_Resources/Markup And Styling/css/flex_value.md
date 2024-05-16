\<flex\>
========

Baseline: [Widely supported]
---------------------------------------

Baseline is determined by this web feature being supported on the
current and the previous major versions of major browsers.

- [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-unified-view-stable-web-features/)
- [See full compatibility](#browser_compatibility)

The `<flex>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) denotes a flexible length within a grid
container. It is used in
[`grid-template-columns`](grid-template-columns.md),
[`grid-template-rows`](grid-template-rows.md) and other related properties.

Syntax
------

The `<flex>` data type is specified as a [`<number>`](number.md) followed
by the unit `fr`. The `fr` unit represents a fraction of the leftover
space in the grid container. As with all CSS dimensions, there is no
space between the unit and the number.

Examples
--------

### Examples of correct values for the fr data type

```
1fr    /* Using an integer value */
2.5fr  /* Using a float value */
```

### Example of use in a tracklisting for CSS Grid layout

[css]

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr 2.5fr 1.5fr;
}
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Grid Layout Module Level 2\
  [\# fr-unit]](https://drafts.csswg.org/css-grid/#fr-unit)

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

`flex_value`

29

12

40

10

28

10.1

57

29

40

28

10.3

2.0

See also
--------

- [CSS Grid Layout](css_grid_layout.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/flex_value>

place-content
=============

The `place-content`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](shorthand_properties.md) allows you to align content along both
the block and inline directions at once (i.e. the
[`align-content`](align-content.md) and
[`justify-content`](justify-content.md) properties) in a relevant layout
system such as [Grid](css_grid_layout.md) or
[Flexbox](css_flexible_box_layout.md).

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`align-content`](align-content.md)
- [`justify-content`](justify-content.md)

Syntax
------

[css]

```css
/* Positional alignment */
/* align-content does not take left and right values */
place-content: center start;
place-content: start center;
place-content: end left;
place-content: flex-start center;
place-content: flex-end center;

/* Baseline alignment */
/* justify-content does not take baseline values */
place-content: baseline center;
place-content: first baseline space-evenly;
place-content: last baseline right;

/* Distributed alignment */
place-content: space-between space-evenly;
place-content: space-around space-evenly;
place-content: space-evenly stretch;
place-content: stretch space-evenly;

/* Global values */
place-content: inherit;
place-content: initial;
place-content: revert;
place-content: revert-layer;
place-content: unset;
```

The first value is the [`align-content`](align-content.md) property value,
the second the [`justify-content`](justify-content.md) one.

**Note:** If the second value is not present, the first value is used
for both, provided it is a valid value for both. If it is invalid for
one or the other, the whole value will be invalid.

### Values

[`start`](#start)

:   The items are packed flush to each other toward the start edge of
    the alignment container in the appropriate axis.

[`end`](#end)

:   The items are packed flush to each other toward the end edge of the
    alignment container in the appropriate axis.

[`flex-start`](#flex-start)

:   The items are packed flush to each other toward the edge of the
    alignment container depending on the flex container\'s main-start or
    cross-start side. This only applies to flex layout items. For items
    that are not children of a flex container, this value is treated
    like `start`.

[`flex-end`](#flex-end)

:   The items are packed flush to each other toward the edge of the
    alignment container depending on the flex container\'s main-end or
    cross-end side. This only applies to flex layout items. For items
    that are not children of a flex container, this value is treated
    like `end`.

[`center`](#center)

:   The items are packed flush to each other toward the center of the
    alignment container.

[`left`](#left)

:   The items are packed flush to each other toward the left edge of the
    alignment container. If the property\'s axis is not parallel with
    the inline axis, this value behaves like `start`.

[`right`](#right)

:   The items are packed flush to each other toward the right edge of
    the alignment container in the appropriate axis. If the property\'s
    axis is not parallel with the inline axis, this value behaves like
    `start`.

[`space-between`](#space-between)

:   The items are evenly distributed within the alignment container. The
    spacing between each pair of adjacent items is the same. The first
    item is flush with the main-start edge, and the last item is flush
    with the main-end edge.

[`baseline`](#baseline), `first baseline`, `last baseline`

:   Specifies participation in first- or last-baseline alignment: aligns
    the alignment baseline of the box\'s first or last baseline set with
    the corresponding baseline in the shared first or last baseline set
    of all the boxes in its baseline-sharing group. The fallback
    alignment for `first baseline` is `start`, the one for
    `last baseline` is `end`.

[`space-around`](#space-around)

:   The items are evenly distributed within the alignment container. The
    spacing between each pair of adjacent items is the same. The empty
    space before the first and after the last item equals half of the
    space between each pair of adjacent items.

[`space-evenly`](#space-evenly)

:   The items are evenly distributed within the alignment container. The
    spacing between each pair of adjacent items, the main-start edge and
    the first item, and the main-end edge and the last item, are all
    exactly the same.

[`stretch`](#stretch)

:   If the combined size of the items is less than the size of the
    alignment container, any `auto`-sized items have their size
    increased equally (not proportionally), while still respecting the
    constraints imposed by
    [`max-height`](max-height.md)/[`max-width`](max-width.md) (or equivalent
    functionality), so that the combined size exactly fills the
    alignment container

[`safe`](#safe)

:   Used alongside an alignment keyword. If the chosen keyword means
    that the item overflows the alignment container causing data loss,
    the item is instead aligned as if the alignment mode were `start`.

[`unsafe`](#unsafe)

:   Used alongside an alignment keyword. Regardless of the relative
    sizes of the item and alignment container, and regardless of whether
    overflow which causes data loss might happen, the given alignment
    value is honored.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`align-content`](align-content.md): |
|                                   |     `normal`                      |
|                                   | -   [](justify-content.md): |
|                                   |     `normal`                      |
+-----------------------------------+-----------------------------------+
| Applies to                        | multi-line flex containers        |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -                                 |
|                                   | [`align-content`](align-content.md): |
|                                   |     as specified                  |
|                                   | -   [](justify-content.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | discrete                          |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
place-content = 
  <'align-content'> <'justify-content'>?  
```

Examples
--------

### Placing content in a flex container

#### HTML

[html]

```html
<div id="container">
  <div class="small">Lorem</div>
  <div class="small">Lorem<br />ipsum</div>
  <div class="large">Lorem</div>
  <div class="large">Lorem<br />ipsum</div>
  <div class="large"></div>
  <div class="large"></div>
</div>
```

#### CSS

[css]

```css
#container {
  display: flex;
  height: 240px;
  width: 240px;
  flex-wrap: wrap;
  background-color: #8c8c8c;
  writing-mode: horizontal-tb; /* Can be changed in the live sample */
  direction: ltr; /* Can be changed in the live sample */
  place-content: flex-end center; /* Can be changed in the live sample */
}

div > div {
  border: 2px solid #8c8c8c;
  width: 50px;
  background-color: #a0c8ff;
}

.small {
  font-size: 12px;
  height: 40px;
}

.large {
  font-size: 14px;
  height: 50px;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\#
  place-content]](https://drafts.csswg.org/css-align/#place-content)

  ----------------------------------------------------------------------------

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

`place-content`

59

79

45

No

46

9

59

59

45

43

9

7.0

`flex_context`

59

79

45Starting with version 60, you can only specify a single value if it is
valid for both `align-content` and `justify-content`.

No

46

9

59

59

45Starting with version 60, you can only specify a single value if it is
valid for both `align-content` and `justify-content`.

43

9

7.0

`grid_context`

59

79

53Starting with version 60, you can only specify a single value if it is
valid for both `align-content` and `justify-content`.

No

46

11

59

59

53Starting with version 60, you can only specify a single value if it is
valid for both `align-content` and `justify-content`.

43

11

7.0

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](aligning_items_in_a_flex_container.md)*
- CSS Grid Guide: *[](_Resources/Markup%20And%20Styling/css/css_grid_layout/box_alignment_in_grid_layout.md)*
- [CSS Box Alignment](css_box_alignment.md)
- The [`align-content`](align-content.md) property
- The [`justify-content`](justify-content.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/place-content>

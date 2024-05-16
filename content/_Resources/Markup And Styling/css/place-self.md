place-self
==========

The `place-self` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[shorthand property](shorthand_properties.md) allows you to align an
individual item in both the block and inline directions at once (i.e.
the [`align-self`](align-self.md) and [`justify-self`](justify-self.md)
properties) in a relevant layout system such as [Grid](css_grid_layout.md)
or [Flexbox](css_flexible_box_layout.md). If the second value is not
present, the first value is also used for it.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`align-self`](align-self.md)
- [`justify-self`](justify-self.md)

Syntax
------

[css]

```css
/* Keyword values */
place-self: auto center;
place-self: normal start;

/* Positional alignment */
place-self: center normal;
place-self: start auto;
place-self: end normal;
place-self: self-start auto;
place-self: self-end normal;
place-self: flex-start auto;
place-self: flex-end normal;

/* Baseline alignment */
place-self: baseline normal;
place-self: first baseline auto;
place-self: last baseline normal;
place-self: stretch auto;

/* Global values */
place-self: inherit;
place-self: initial;
place-self: revert;
place-self: revert-layer;
place-self: unset;
```

### Values

[`auto`](#auto)

:   Computes to the parent\'s [`align-items`](align-items.md) value.

[`normal`](#normal)

:   The effect of this keyword is dependent of the layout mode we are
    in:

    -   In absolutely-positioned layouts, the keyword behaves like
        `start` on *replaced* absolutely-positioned boxes, and as
        `stretch` on *all other* absolutely-positioned boxes.
    -   In static position of absolutely-positioned layouts, the keyword
        behaves as `stretch`.
    -   For flex items, the keyword behaves as `stretch`.
    -   For grid items, this keyword leads to a behavior similar to the
        one of `stretch`, except for boxes with an aspect ratio or an
        intrinsic sizes where it behaves like `start`.
    -   The property doesn\'t apply to block-level boxes, and to table
        cells.

[`self-start`](#self-start)

:   Aligns the items to be flush with the edge of the alignment
    container corresponding to the item\'s start side in the cross axis.

[`self-end`](#self-end)

:   Aligns the items to be flush with the edge of the alignment
    container corresponding to the item\'s end side in the cross axis.

[`flex-start`](#flex-start)

:   The cross-start margin edge of the flex item is flushed with the
    cross-start edge of the line.

[`flex-end`](#flex-end)

:   The cross-end margin edge of the flex item is flushed with the
    cross-end edge of the line.

[`center`](#center)

:   The flex item\'s margin box is centered within the line on the
    cross-axis. If the cross-size of the item is larger than the flex
    container, it will overflow equally in both directions.

[`baseline`](#baseline), `first baseline`. `last baseline`

:   Specifies participation in first- or last-baseline alignment: aligns
    the alignment baseline of the box\'s first or last baseline set with
    the corresponding baseline in the shared first or last baseline set
    of all the boxes in its baseline-sharing group. The fallback
    alignment for `first baseline` is `start`, the one for
    `last baseline` is `end`.

[`stretch`](#stretch)

:   If the combined size of the items along the cross axis is less than
    the size of the alignment container and the item is `auto`-sized,
    its size is increased equally (not proportionally), while still
    respecting the constraints imposed by
    [`max-height`](max-height.md)/[`max-width`](max-width.md) (or equivalent
    functionality), so that the combined size of all `auto`-sized items
    exactly fills the alignment container along the cross axis.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`align-self`](align-self.md):   |
|                                   |     `auto`                        |
|                                   | -                                 |
|                                   |   [`justify-self`](justify-self.md): |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | block-level boxes,                |
|                                   | absolutely-positioned boxes, and  |
|                                   | grid items                        |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [`align-self`](align-self.md):   |
|                                   |     `auto` computes to itself on  |
|                                   |     absolutely-positioned         |
|                                   |     elements, and to the computed |
|                                   |     value of                      |
|                                   |     [`align-items`](align-items.md)  |
|                                   |     on the parent (minus any      |
|                                   |     legacy keywords) on all other |
|                                   |     boxes, or `start` if the box  |
|                                   |     has no parent. Its behavior   |
|                                   |     depends on the layout model,  |
|                                   |     as described for              |
|                                   |                                   |
|                                   |   [`justify-self`](justify-self.md). |
|                                   |     Otherwise the specified       |
|                                   |     value.                        |
|                                   | -                                 |
|                                   |   [`justify-self`](justify-self.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | discrete                          |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
place-self = 
  <'align-self'> <'justify-self'>?  
```

Examples
--------

### Simple demonstration

In the following example we have a simple 2 x 2 grid layout. Initially
the grid container has [`justify-items`](justify-items.md) and
[`align-items`](align-items.md) values of `stretch` --- the defaults ---
which causes the grid items to stretch across the entire width of their
cells.

The second, third, and fourth grid items are then given different values
of `place-self`, to show how these override the default placements.
These values cause the grid items to span only as wide/tall as their
content width/height, and align in different positions across their
cells, in the block and inline directions.

#### HTML

[html]

```html
<article class="container">
  <span>First</span>
  <span>Second</span>
  <span>Third</span>
  <span>Fourth</span>
</article>
```

#### CSS

[css]

```css
html {
  font-family: helvetica, arial, sans-serif;
  letter-spacing: 1px;
}

article {
  background-color: red;
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-auto-rows: 80px;
  grid-gap: 10px;
  margin: 20px;
  width: 300px;
}

span:nth-child(2) {
  place-self: start center;
}

span:nth-child(3) {
  place-self: center start;
}

span:nth-child(4) {
  place-self: end;
}

article span {
  background-color: black;
  color: white;
  margin: 1px;
  text-align: center;
}

article,
span {
  padding: 10px;
  border-radius: 7px;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Box Alignment Module Level 3\
  [\#
  place-self-property]](https://drafts.csswg.org/css-align/#place-self-property)

  ----------------------------------------------------------------------------------------

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

`place-self`

59

79

45

No

46

11

59

59

45

43

11

7.0

`flex_context`

59

79

45

No

46

11

59

59

45

43

11

7.0

`grid_context`

59

79

45

No

46

11

59

59

45

43

11

7.0

See also
--------

- CSS Flexbox Guide: *[](basic_concepts_of_flexbox.md)*
- CSS Flexbox Guide: *[](aligning_items_in_a_flex_container.md)*
- CSS Grid Guide: *[](_Resources/Markup%20And%20Styling/css/css_grid_layout/box_alignment_in_grid_layout.md)*
- [CSS Box Alignment](css_box_alignment.md)
- The [`align-self`](align-self.md) property
- The [`justify-self`](justify-self.md) property

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/place-self>

Logical properties for margins, borders, and padding
====================================================

The [Logical Properties and Values
specification](https://drafts.csswg.org/css-logical/) defines
flow-relative mappings for the various margin, border, and padding
properties and their shorthands. In this guide, we take a look at these.

If you have looked at the main page for the [](css_logical_properties_and_values.md) module, you will see there
are a huge number of properties listed. This is mostly because there are
four longhand values each for margin, border, and padding side, plus all
the shorthand values.

Mappings for margins, borders, and padding
------------------------------------------

The specification details mappings for each logical value to a physical
counterpart. In the table below I have given these mapped values
assuming that the [`writing-mode`](writing-mode.md) in use is
`horizontal-tb` --- with a left to right direction. The inline direction
therefore runs horizontally --- left to right --- and
[`margin-inline-start`](margin-inline-start.md) would be equivalent to
[`margin-left`](margin-left.md).

If you were using a `horizontal-tb` writing mode with a right-to-left
text direction then [`margin-inline-start`](margin-inline-start.md)
would be the same as [`margin-right`](margin-right.md), and in a
vertical writing mode it would be the same as using
[`margin-top`](margin-top.md).

  Logical property                                              Physical Property
  ------------------------------------------------------------- ---------------------------------------------------------------
  [`border-block-end`](border-block-end.md)                     [`border-bottom`](border-bottom.md)
  [`border-block-end-color`](border-block-end-color.md)         [`border-bottom-color`](border-bottom-color.md)
  [`border-block-end-style`](border-block-end-style.md)         [`border-bottom-style`](border-bottom-style.md)
  [`border-block-end-width`](border-block-end-width.md)         [`border-bottom-width`](border-bottom-width.md)
  [`border-block-start`](border-block-start.md)                 [`border-top`](border-top.md)
  [`border-block-start-color`](border-block-start-color.md)     [`border-top-color`](border-top-color.md)
  [`border-block-start-style`](border-block-start-style.md)     [`border-top-style`](border-top-style.md)
  [`border-block-start-width`](border-block-start-width.md)     [`border-top-width`](border-top-width.md)
  [`border-inline-end`](border-inline-end.md)                   [`border-right`](border-right.md)
  [`border-inline-end-color`](border-inline-end-color.md)       [`border-right-color`](border-right-color.md)
  [`border-inline-end-style`](border-inline-end-style.md)       [`border-right-style`](border-right-style.md)
  [`border-inline-end-width`](border-inline-end-width.md)       [`border-right-width`](border-right-width.md)
  [`border-inline-start`](border-inline-start.md)               [`border-left`](border-left.md)
  [`border-inline-start-color`](border-inline-start-color.md)   [`border-left-color`](border-left-color.md)
  [`border-inline-start-style`](border-inline-start-style.md)   [`border-left-style`](border-left-style.md)
  [`border-inline-start-width`](border-inline-start-width.md)   [`border-left-width`](border-left-width.md)
  [`border-start-start-radius`](border-start-start-radius.md)   [`border-top-left-radius`](border-top-left-radius.md)
  [`border-end-start-radius`](border-end-start-radius.md)       [`border-bottom-left-radius`](border-bottom-left-radius.md)
  [`border-start-end-radius`](border-start-end-radius.md)       [`border-top-right-radius`](border-top-right-radius.md)
  [`border-end-end-radius`](border-end-end-radius.md)           [`border-bottom-right-radius`](border-bottom-right-radius.md)
  [`margin-block-end`](margin-block-end.md)                     [`margin-bottom`](margin-bottom.md)
  [`margin-block-start`](margin-block-start.md)                 [`margin-top`](margin-top.md)
  [`margin-inline-end`](margin-inline-end.md)                   [`margin-right`](margin-right.md)
  [`margin-inline-start`](margin-inline-start.md)               [`margin-left`](margin-left.md)
  [`padding-block-end`](padding-block-end.md)                   [`padding-bottom`](padding-bottom.md)
  [`padding-block-start`](padding-block-start.md)               [`padding-top`](padding-top.md)
  [`padding-inline-end`](padding-inline-end.md)                 [`padding-right`](padding-right.md)
  [`padding-inline-start`](padding-inline-start.md)             [`padding-left`](padding-left.md)

There are also some additional shorthands, made possible because we can
target both block or both inline edges of the box simultaneously. These
shorthands have no physical equivalent.

  Property                                          Purpose
  ------------------------------------------------- ------------------------------------------------------------------------------------------------------------------------------------------
  [`border-block`](border-block.md)                 Sets [`border-color`](border-color.md), [`border-style`](border-style.md), and [`border-width`](border-width.md) for both block borders.
  [`border-block-color`](border-block-color.md)     Sets `border-color` for both block borders.
  [`border-block-style`](border-block-style.md)     Sets `border-style` for both block borders.
  [`border-block-width`](border-block-width.md)     Sets `border-width` for both block borders.
  [`border-inline`](border-inline.md)               Sets `border-color`, `-style`, and `-width` for both inline borders.
  [`border-inline-color`](border-inline-color.md)   Sets `border-color` for both inline borders.
  [`border-inline-style`](border-inline-style.md)   Sets `border-style` for both inline borders.
  [`border-inline-width`](border-inline-width.md)   Sets `border-width` for both inline borders.
  [`margin-block`](margin-block.md)                 Sets all the block [`margin`](margin.md)s.
  [`margin-inline`](margin-inline.md)               Sets all the inline `margin`s.
  [`padding-block`](padding-block.md)               Sets the block [`padding`](padding.md).
  [`padding-inline`](padding-inline.md)             Sets the inline `padding`.

Margin examples
---------------

The mapped margin properties of
[`margin-inline-start`](margin-inline-start.md),
[`margin-inline-end`](margin-inline-end.md),
[`margin-block-start`](margin-block-start.md), and
[`margin-inline-end`](margin-inline-end.md) can be used instead of their
physical counterparts.

In the example below I have created two boxes and added different sized
margins to each edge. I have added an extra container with a border to
make the margin more obvious to see.

One box uses physical properties and the other logical properties. Try
changing the [`direction`](direction.md) property to `rtl` to cause the
boxes to display in a right-to-left direction, the margins on the first
box will stay in the same place, while the margins on the inline
dimension of the second box will switch.

You can also try changing the `writing-mode` from `horizontal-tb` to
`vertical-rl`. Again, notice how the margins stay in the same place for
the first box, but switch around to follow the text direction in the
second.

### Margin shorthands

As we can now target both sides of a box --- either both inline sides or
both block sides --- there are new shorthands available,
[`margin-inline`](margin-inline.md) and
[`margin-block`](margin-block.md), which accept two values. The first
value will apply to the start of that dimension, the second to the end.
If you only use one value it is applied to both.

In a horizontal writing mode this CSS would apply a 5px margin to the
top of the box and a 10px margin to the bottom.

[css]

```css
.box {
  margin-block: 5px 10px;
}
```

Padding examples
----------------

The mapped padding properties of
[`padding-inline-start`](padding-inline-start.md),
[`padding-inline-end`](padding-inline-end.md),
[`padding-block-start`](padding-block-start.md), and
[`padding-inline-end`](padding-inline-end.md) can be used instead of
their physical counterparts.

In the example below I have two boxes, one of which is using physical
padding properties and the other logical padding properties. With a
`writing-mode` of `horizontal-tb`, both boxes should appear the same.

Try changing the `direction` property to `rtl` to cause the boxes to
display in a right-to-left direction. The padding on the first box will
stay in the same place, whereas the padding on the inline dimension of
the second box will switch.

You can also try changing the `writing-mode` from `horizontal-tb` to
`vertical-rl`. Again, notice how the padding stays in the same place for
the first box, but switches around to follow the text direction in the
second.

### Padding shorthands

As with margin, there are two-value shorthands for padding ---
[`padding-inline`](padding-inline.md) and
[`padding-block`](padding-block.md) --- which allow you to set the
padding of the two inline, and two block dimensions, respectively.

In a horizontal `writing-mode` this CSS would apply `5px` of padding to
the top of the box and 10px of padding to the bottom:

[css]

```css
.box {
  padding-block: 5px 10px;
}
```

Border examples
---------------

The border properties are the main reason that Logical Properties and
Values seems to have so many properties, as we have the longhands for
the color, width, and style of the border on each side of a box, along
with the shorthand to set all three at once for each side. As with
margin and padding we have a mapped version of each physical property.

The demo below uses some longhands and three shorthand values. As with
the other demos try changing the `direction` property to `rtl` to cause
the boxes to display in a right-to-left direction, or changing the
`writing-mode` from `horizontal-tb` to `vertical-rl`.

### New border shorthands

There are two-value shorthands to set the width, style, and color of the
block or inline dimension, and shorthands to set all three values in the
block or inline dimension. The below code, in a horizontal writing mode,
would give you a 2px green solid border on the top and bottom of the
box, and a 4px dotted purple border on the left and right.

[css]

```css
.box {
  border-block: 2px solid green;
  border-inline-width: 4px;
  border-inline-style: dotted;
  border-inline-color: rebeccapurple;
}
```

### Flow relative border-radius properties

The specification has flow-relative equivalents for the
[`border-radius`](border-radius.md) longhands. The below example, in a
horizontal `writing-mode`, would set the top-right border radius to 1em,
the bottom-right to 0, the bottom-left to 20px and the top-left to 40px.

[css]

```css
.box {
  border-end-start-radius: 1em;
  border-end-end-radius: 0;
  border-start-end-radius: 20px;
  border-start-start-radius: 40px;
}
```

Indicating logical values for the 4-value shorthand syntax
----------------------------------------------------------

The specification makes a suggestion for the four-value shorthands such
as the `margin` property, however the final decision on how this should
be indicated is as yet unresolved, and is discussed in [this
issue](https://github.com/w3c/csswg-drafts/issues/1282).

Using any four-value shorthand such as `margin`, `padding`, or `border`
will currently use the physical versions, so if following the flow of
the document is important, use the longhand properties for the time
being.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_logical_properties_and_values/Margins_borders_padding>

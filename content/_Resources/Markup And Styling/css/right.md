right
=====

The `right` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property participates in specifying the horizontal position of a
[positioned element](position.md). It has no effect on non-positioned
elements.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
right: 3px;
right: 2.4em;

/* <percentage>s of the width of the containing block */
right: 10%;

/* Keyword value */
right: auto;

/* Global values */
right: inherit;
right: initial;
right: revert;
right: revert-layer;
right: unset;
```

### Values

[`<length>`](length.md)

:   A negative, null, or positive [`<length>`](length.md) that represents:

    -   for *absolutely positioned elements*, the distance to the right
        edge of the containing block.
    -   for *relatively positioned elements*, the distance that the
        element is moved to the left of its normal position.

[`<percentage>`](percentage.md)

:   A [`<percentage>`](percentage.md) of the containing block\'s width.

[`auto`](#auto)

:   Specifies that:

    -   for *absolutely positioned elements*, the position of the
        element is based on the [`left`](left) property, while
        `width: auto` is treated as a width based on the content; or if
        `left` is also `auto`, the element is positioned where it should
        horizontally be positioned if it were a static element.
    -   for *relatively positioned elements*, the distance of the
        element from its normal position is based on the [`left`](left)
        property; or if `left` is also `auto`, the element is not moved
        horizontally at all.

[`inherit`](#inherit)

:   Specifies that the value is the same as the computed value from its
    parent element (which might not be its containing block). This
    computed value is then handled as if it were a [`<length>`](length.md),
    [`<percentage>`](percentage.md), or the `auto` keyword.

Description
-----------

The effect of `right` depends on how the element is positioned (i.e.,
the value of the [`position`](position.md) property):

- When `position` is set to `absolute` or `fixed`, the `right`
    property specifies the distance between the element\'s outer margin
    of right edge and the inner border of the right edge of its
    containing block.
- When `position` is set to `relative`, the `right` property specifies
    the distance the element\'s right edge is moved to the left from its
    normal position.
- When `position` is set to `sticky`, the `right` property is used to
    compute the sticky-constraint rectangle.
- When `position` is set to `static`, the `right` property has *no
    effect*.

When both [`left`](left.md) and `right` are defined, if not prevented from
doing so by other properties, the element will stretch to satisfy both.
If the element cannot stretch to satisfy both --- for example, if a
`width` is declared --- the position of the element is
*over-constrained*. When this is the case, the `left` value has
precedence when the container is left-to-right; the `right` value has
precedence when the container is right-to-left.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         positioned elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, `auto`
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
right = 
  auto                 |
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Absolute and relative positioning using right

#### HTML

[html]

```html
<div id="relative">Relatively positioned</div>
<div id="absolute">Absolutely positioned</div>
```

#### CSS

[css]

```css
#relative {
  width: 100px;
  height: 100px;
  background-color: #ffc7e4;
  position: relative;
  top: 20px;
  left: 20px;
}

#absolute {
  width: 100px;
  height: 100px;
  background-color: #ffd7c2;
  position: absolute;
  bottom: 10px;
  right: 20px;
}
```

#### Result

### Declaring both left and right

When both `left` and `right` are declared, the element will stretch to
meet both, unless other constraints prevent it from doing so. If the
element will not stretch or shrink to meet both. When the position of
the element is *overspecified*, the precedence is based on the
container\'s direction: The `left` will take precedence if the
container\'s direction is left-to-right. The `right` will take
precedence if the container\'s direction is right-to-left.

#### HTML

[html]

```html
<div id="parent">
  Parent
  <div id="noWidth">No width</div>
  <div id="width">width: 100px</div>
</div>
```

#### CSS

[css]

```css
div {
  outline: 1px solid #cccccc;
}
#parent {
  width: 200px;
  height: 200px;
  background-color: #ffc7e4;
  position: relative;
}
/* declare both a left and a right */
#width,
#noWidth {
  background-color: #c2ffd7;
  position: absolute;
  left: 0;
  right: 0;
}
/* declare a width */
#width {
  width: 100px;
  top: 60px;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Positioned Layout Module Level 3\
  [\# insets]](https://drafts.csswg.org/css-position/#insets)

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

`right`

1

12

1

5.5

5

1

4.4

18

4

14

1

1.0

See also
--------

- [`inset`](_Resources/Markup%20And%20Styling/css/inset.md), the shorthand for all related properties:
    [`top`](top.md), [`bottom`](bottom.md), [`left`](left.md), and
    [`right`](right.md)
- The mapped logical properties:
    [`inset-block-start`](inset-block-start.md),
    [`inset-block-end`](inset-block-end.md),
    [`inset-inline-start`](inset-inline-start.md), and
    [`inset-inline-end`](inset-inline-end.md) and the shorthands
    [`inset-block`](inset-block.md) and [`inset-inline`](inset-inline.md)
- [`position`](position.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/right>

bottom
======

The `bottom` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property participates in setting the vertical position of a [](position.md). It has no effect on non-positioned elements.

Try it
------

The effect of `bottom` depends on how the element is positioned (i.e.,
the value of the [`position`](position.md) property):

- When `position` is set to `absolute` or `fixed`, the `bottom`
    property specifies the distance between the outer edge of the
    element\'s [](introduction_to_the_css_box_model.md) and the
    outer edge of the containing block\'s bottom padding.
- When `position` is set to `relative`, the `bottom` property
    specifies the distance the element\'s bottom edge is moved above its
    normal position.
- When `position` is set to `sticky`, the `bottom` property is used to
    compute the sticky-constraint rectangle.
- When `position` is set to `static`, the `bottom` property has *no
    effect*.

When both [`top`](top.md) and `bottom` are specified, `position` is set to
`absolute` or `fixed`, *and* [`height`](_Resources/Markup%20And%20Styling/css/height.md) is unspecified (either
`auto` or `100%`) both the `top` and `bottom` distances are respected.
In all other situations, if [`height`](_Resources/Markup%20And%20Styling/css/height.md) is constrained in any way
or `position` is set to `relative`, the `top` property takes precedence
and the `bottom` property is ignored.

Syntax
------

[css]

```css
/* <length> values */
bottom: 3px;
bottom: 2.4em;

/* <percentage>s of the height of the containing block */
bottom: 10%;

/* Keyword value */
bottom: auto;

/* Global values */
bottom: inherit;
bottom: initial;
bottom: revert;
bottom: revert-layer;
bottom: unset;
```

### Values

[`<length>`](length.md)

:   A negative, null, or positive [`<length>`](length.md) that represents:

    -   for *absolutely positioned elements*, the distance to the bottom
        edge of the containing block.
    -   for *relatively positioned elements*, the distance that the
        element is moved above its normal position.

[`<percentage>`](percentage.md)

:   A [`<percentage>`](percentage.md) of the containing block\'s height.

[`auto`](#auto)

:   Specifies that:

    -   for *absolutely positioned elements*, the position of the
        element is based on the [`top`](top) property, while
        `height: auto` is treated as a height based on the content; or
        if `top` is also `auto`, the element is positioned where it
        should vertically be positioned if it were a static element.
    -   for *relatively positioned elements*, the distance of the
        element from its normal position is based on the [`top`](top)
        property; or if `top` is also `auto`, the element is not moved
        vertically at all.

[`inherit`](#inherit)

:   Specifies that the value is the same as the computed value from its
    parent element (which might not be its containing block). This
    computed value is then handled as if it were a [`<length>`](length.md),
    [`<percentage>`](percentage.md), or the `auto` keyword.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         positioned elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to the height of the containing block
  [Computed value](computed_value.md)   if specified as a length, the corresponding absolute length; if specified as a percentage, the specified value; otherwise, `auto`
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
bottom = 
  auto                 |
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Absolute and fixed positioning

This example demonstrates the difference in behavior of the `bottom`
property, when [`position`](position.md) is `absolute` versus `fixed`.

#### HTML

[html]

```html
<p>
  This<br />is<br />some<br />tall,<br />tall,<br />tall,<br />tall,<br />tall<br />content.
</p>
<div class="fixed"><p>Fixed</p></div>
<div class="absolute"><p>Absolute</p></div>
```

#### CSS

[css]

```css
p {
  font-size: 30px;
  line-height: 2em;
}

div {
  width: 48%;
  text-align: center;
  background: rgba(55, 55, 55, 0.2);
  border: 1px solid blue;
}

.absolute {
  position: absolute;
  bottom: 0;
  left: 0;
}

.fixed {
  position: fixed;
  bottom: 0;
  right: 0;
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

`bottom`

1

12

1

5In Internet Explorer versions before 7, when both `top` and `bottom`
are specified, the element position is overconstrained and the `top`
property has precedence; the computed value of `bottom` is set to
`-top`, while its specified value is ignored.

6

1

≤37

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
https://developer.mozilla.org/en-US/docs/Web/CSS/bottom>

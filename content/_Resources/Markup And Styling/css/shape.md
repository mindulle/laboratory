\<shape\>
=========

**Deprecated:** This feature is no longer recommended. Though some
browsers might still support it, it may have already been removed from
the relevant web standards, may be in the process of being dropped, or
may only be kept for compatibility purposes. Avoid using it, and update
existing code if possible; see the [compatibility
table](#browser_compatibility) at the bottom of this page to guide your
decision. Be aware that this feature may cease to work at any time.

The `<shape>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) defines the specific form (shape) of a region.
The region represents the part of an element to which the [`clip`](clip.md)
property applies.

**Note:** `<shape>` and `rect()` work in conjunction with
[`clip`](clip.md), which has been deprecated in favor of
[`clip-path`](clip-path.md). When possible, use `clip-path` and the
[`<basic-shape>`](basic-shape.md) data type instead.

Syntax
------

The `<shape>` data type is specified using the `rect()` function, which
produces a region in the form of a rectangle.

`rect()`

[css]

```css
rect(top, right, bottom, left)
```

### Values

[*top*](#top)

:   Is a [`<length>`](length.md) representing the offset for the top of the
    rectangle relative to the top border of the element\'s box.

[*right*](#right)

:   Is a [`<length>`](length.md) representing the offset for the right of
    the rectangle relative to the left border of the element\'s box.

[*bottom*](#bottom)

:   Is a [`<length>`](length.md) representing the offset for the bottom of
    the rectangle relative to the top border of the element\'s box.

[*left*](#left)

:   Is a [`<length>`](length.md) representing the offset for the left of
    the rectangle relative to the left border of the element\'s box.

Interpolation
-------------

When animated, values of the `<shape>` data type are interpolated over
their `top`, `right`, `bottom`, and `left` components, each treated as a
real, floating-point number. The speed of the interpolation is
determined by the [easing function](easing-function.md) associated with the
animation.

Example
-------

### Example demonstrating correct use of the rect() function

[css]

```css
img.clip04 {
  clip: rect(10px, 20px, 20px, 10px);
}
```

Specifications
--------------

  ---------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------

  [Cascading Style Sheets Level 2 Revision 2 (CSS 2.2) Specification\
  [\#
  value-def-shape]](https://drafts.csswg.org/css2/#value-def-shape)

  ---------------------------------------------------------------------------

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

`shape`

1

12

1

5.5

9.5

1.3

37

18

4

14

1

1.0

`rect`

1

12

1

5.5For Internet Explorer versions 5.5 through 7, the `rect()` function
uses spaces (instead of commas) to separate parameters. For Internet
Explorer 8 and later versions, only the standard comma-separated syntax
is supported.

9.5

1.3

37

18

4

14

1

1.0

See also
--------

- Related CSS property: [`clip`](clip.md)
- The [`-moz-image-rect()`](-moz-image-rect.md) function has similar
    coordinate values to `rect()`.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/shape>

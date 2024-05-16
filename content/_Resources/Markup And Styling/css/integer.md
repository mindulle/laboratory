\<integer\>
===========

The `<integer>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) is a special type of [`<number>`](number.md) that
represents a positive or negative whole number. Integers can be used in
numerous CSS properties and descriptors, such as the
[`column-count`](column-count.md),
[`counter-increment`](counter-increment.md), [`grid-column`](grid-column.md),
[`grid-row`](grid-row.md), and [`z-index`](z-index.md) properties and the
[`range`](range.md) descriptor.

Syntax
------

The `<integer>` data type consists of one or several decimal digits, 0
through 9 inclusive, optionally preceded by a single `+` or `-` sign.
There is no unit associated with integers.

**Note:** There is no official range of valid `<integer>` values, and
the specifications do not specify a range.

Interpolation
-------------

When animated, values of the `<integer>` data type are
[interpolated](https://developer.mozilla.org/en-US/docs/Glossary/Interpolation)
using discrete, whole steps. The calculation is done as if they were
real, floating-point numbers; the discrete value is obtained using the
[floor function](https://en.wikipedia.org/wiki/Floor_function). The
speed of the interpolation is determined by the [](easing-function.md) associated with the animation.

Examples
--------

### Valid integers

```text
12          Positive integer (without a leading + sign)
+123        Positive integer (with a leading + sign)
-456        Negative integer
0           Zero
+0          Zero, with a leading +
-0          Zero, with a leading -
```

### Invalid integers

```text
12.0        This is a <number>, not an <integer>, though it represents an integer.
12.         Decimal points are not allowed.
+---12      Only one leading +/- is allowed.
ten         Letters are not allowed.
_5          Special characters are not allowed.
\35         Escaped Unicode characters are not allowed, even if they are an integer (here: 5).
\4E94       Non-arabic numerals are not allowed, even when escaped (here: the Japanese 5, 五).
3e4         Scientific notation is not allowed.
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# integers]](https://drafts.csswg.org/css-values/#integers)

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

`integer`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

See also
--------

- [`<number>`](number.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/integer>

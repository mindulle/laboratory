\<number\>
==========

The `<number>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents a number, being either an integer or a
number with a fractional component.

Syntax
------

The syntax of `<number>` extends the syntax of [`<integer>`](integer.md). A
fractional value is represented by a `.` followed by one or more decimal
digits, and may be appended to an integer. There is no unit associated
with numbers.

Interpolation
-------------

When animated, values of the `<number>` CSS data type are interpolated
as real, floating-point numbers. The speed of the interpolation is
determined by the [easing function](easing-function.md) associated with the
animation.

Examples
--------

### Valid numbers

```
12          A raw <integer> is also a <number>.
4.01        Positive fraction
-456.8      Negative fraction
0.0         Zero
+0.0        Zero, with a leading +
-0.0        Zero, with a leading -
.60         Fractional number without a leading zero
10e3        Scientific notation
-3.4e-2     Complicated scientific notation
```

### Invalid numbers

```
12.         Decimal points must be followed by at least one digit.
+-12.2      Only one leading +/- is allowed.
12.1.1      Only one decimal point is allowed.
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# numbers]](https://drafts.csswg.org/css-values/#numbers)

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

`number`

1

12

1

5

2

1

4.4

18

4

10.1

1

1.0

`scientific_notation`

43

12

29

11

30

10.1

43

43

29

30

10.3

4.0

See also
--------

- [`<integer>`](integer.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/number>

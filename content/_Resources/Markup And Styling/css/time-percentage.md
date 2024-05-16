\<time-percentage\>
===================

The `<time-percentage>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a value that can be either a
[`<time>`](time.md) or a [`<percentage>`](percentage.md).

Syntax
------

Refer to the documentation for [`<time>`](time.md) and
[`<percentage>`](percentage.md) for details of the individual syntaxes
allowed by this type.

Formal syntax
-------------

```
<time-percentage> = 
  <time>        |
  <percentage>  
```

Examples
--------

### Use in calc()

Where a `<time-percentage>` is specified as an allowable type, this
means that the percentage resolves to a time and therefore can be used
in a [`calc()`](calc.md) expression.

### Valid percentages

```
50%
+50%        Optional plus sign
-50%        Negative percentages are not valid for all properties that accept percentages
```

### Invalid percentages

```
50 %        Space not allowed between the number and the percentage sign
```

### Valid times

```
12s         Positive integer
-456ms      Negative integer
4.3ms       Non-integer
14mS        The unit is case-insensitive, although capital letters are not recommended.
+0s         Zero with a leading + and a unit
-0ms        Zero with a leading - and a unit
```

### Invalid times

```
0           Although unitless zero is allowed for <length>s, it's invalid for <time>s.
12.0        This is a <number>, not a <time>, because it's missing a unit.
7 ms        No space is allowed between the number and the unit.
```

Specifications
--------------

  -------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  mixed-percentages]](https://drafts.csswg.org/css-values/#mixed-percentages)

  -------------------------------------------------------------------------------------

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

`time-percentage`

1

12

4

9

10.1

3.1

2

18

4

10.1

2

1.0

See also
--------

- [`<percentage>`](percentage.md)
- [`<time>`](time.md)
- [CSS Values and Units](css_values_and_units.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/time-percentage>

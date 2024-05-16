\<frequency-percentage\>
========================

The `<frequency-percentage>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a value that can be either a
[`<frequency>`](frequency.md) or a [`<percentage>`](percentage.md). Frequency
values, e.g. the pitch of a speaking voice, are not currently used in
any CSS properties.

Syntax
------

The value of a `<frequency-percentage>` is either a
[`<frequency>`](frequency.md) or a [`<percentage>`](percentage.md); see their
individual reference pages for details about their syntaxes.

Description
-----------

### Use in calc()

Where a `<frequency-percentage>` is specified as an allowable type, this
means that the percentage resolves to a frequency and therefore can be
used in a [`calc()`](calc.md) expression.

Formal syntax
-------------

```
<frequency-percentage> = 
  <frequency>   |
  <percentage>  
```

Examples
--------

### Valid percentage values

```
90% Positive percentage
+90% Positive percentage with leading +
-90% Negative percentage — not valid for all properties that use percentages
```

### Invalid percentage values

```
90 % No space is allowed between the number and the unit
```

### Valid frequency values

```
12Hz     Positive integer
4.3Hz    Non-integer
14KhZ    The unit is case-insensitive, though non-SI capitalization is not recommended.
+0Hz     Zero, with a leading + and a unit
-0kHz    Zero, with a leading - and a unit
```

### Invalid frequency values

```
12.0     This is a <number>, not an <frequency>, because it is missing a unit.
7 Hz     No space is allowed between the number and the unit.
0        Although unitless zero is an allowable <length>, it's an invalid <frequency>.
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

`frequency-percentage`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

- [CSS data types](css_types.md)
- [CSS Values and Units](css_values_and_units.md)
- Related CSS data types:
  - [`<frequency>`](frequency.md)
  - [`<percentage>`](percentage.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/frequency-percentage>

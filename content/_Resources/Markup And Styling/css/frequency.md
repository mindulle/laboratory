\<frequency\>
=============

The `<frequency>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a frequency dimension, such as the pitch of
a speaking voice. It is not currently used in any CSS properties.

Syntax
------

The `<frequency>` data type consists of a [`<number>`](number.md) followed
by one of the units listed below. As with all CSS dimensions, there is
no space between the unit literal and the number.

### Units

#### Hz

:   Represents a frequency in hertz. Examples: `0Hz`, `1500Hz`,
    `10000Hz`.

[`kHz`](#khz)

:   Represents a frequency in kilohertz. Examples: `0kHz`, `1.5kHz`,
    `10kHz`.

**Note:** Although the number `0` is always the same regardless of unit,
the unit may not be omitted. In other words, `0` is invalid and does not
represent `0Hz` or `0kHz`. Though the units are case-insensitive, it is
good practice to use a capital \"H\" for `Hz` and `kHz`, as specified in
the [SI](https://en.wikipedia.org/wiki/International_System_of_Units).

Examples
--------

Valid frequency values:

```
12Hz     Positive integer
4.3Hz    Non-integer
14KhZ    The unit is case-insensitive, though non-SI capitalization is not recommended.
+0Hz     Zero, with a leading + and a unit
-0kHz    Zero, with a leading - and a unit
```

Invalid frequency values:

```
12.0     This is a <number>, not an <frequency>, because it is missing a unit.
7 Hz     No space is allowed between the number and the unit.
0        Although unitless zero is an allowable <length>, it's an invalid <frequency>.
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# frequency]](https://drafts.csswg.org/css-values/#frequency)

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

`frequency`

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

`hz`

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

`khz`

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

- [`<frequency-percentage>`](frequency-percentage.md)
- [CSS Values and Units](css_values_and_units.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/frequency>

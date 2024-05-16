\<dimension\>
=============

The `<dimension>`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [](css_types.md) represents a [`<number>`](number.md) with a unit attached
to it, for example `10px`.

CSS uses dimensions to specify distances ([`<length>`](length.md)),
durations ([`<time>`](time.md)), frequencies ([`<frequency>`](frequency.md)),
resolutions ([`<resolution>`](_Resources/Markup%20And%20Styling/css/resolution.md)), and other quantities.

Syntax
------

The syntax of `<dimension>` is a [`<number>`](number.md) immediately
followed by a unit which is an identifier. Unit identifiers are case
insensitive.

Examples
--------

### Valid dimensions

```
12px      12 pixels
1rem      1 rem
1.2pt     1.2 points
2200ms    2200 milliseconds
5s        5 seconds
200hz     200 Hertz
200Hz     200 Hertz (values are case insensitive)
```

### Invalid dimensions

```
12 px       The unit must come immediately after the number.
12"px"      Units are identifiers and therefore unquoted.
3sec        The seconds unit is abbreviated "s" not "sec".
```

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  dimensions]](https://drafts.csswg.org/css-values/#dimensions)

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

`dimension`

1

12

1

5

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

- [CSS data types](css_types.md)
- [Learn to style HTML using
    CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS)
- CSS distances ([`<length>`](length.md)), durations ([`<time>`](time.md)),
    frequencies ([`<frequency>`](frequency.md)), and resolutions
    ([`<resolution>`](_Resources/Markup%20And%20Styling/css/resolution.md))

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/dimension>

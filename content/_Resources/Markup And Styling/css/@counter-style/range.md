range
=====

When defining custom counter styles, the `range` descriptor lets the
author specify a range of counter values over which the style is
applied. If a counter value is outside the specified range, then the
fallback style will be used to construct the representation of that
marker.

Syntax
------

[css]

```css
/* Keyword value */
range: auto;

/* Range values */
range: 2 5;
range: infinite 10;
range: 6 infinite;
range: infinite infinite;

/* Multiple range values */
range:
  2 5,
  8 10;
range:
  infinite 6,
  10 infinite;
```

### Values

[`auto`](#auto)

:   The range depends on the counter system:

    -   For cyclic, numeric, and fixed systems, the range is negative
        infinity to positive infinity.
    -   For alphabetic and symbolic systems, the range is 1 to positive
        infinity.
    -   For additive systems, the range is 0 to positive infinity.
    -   For extends systems, the range is whatever auto would produce
        for the extended system; if extending a complex predefined style
        (§7 Complex Predefined Counter Styles), the range is the
        style\'s defined range.

[`[ [ | infinite ] ]#`](#_infinite_2_)

:   Defines a comma-separated list of ranges. For each individual range,
    the first value is the lower bound and the second value is the upper
    bound. A range is inclusive, that means it always contains both, the
    lower and upper bound numbers. If infinite is used as the first
    value in a range, it represents negative infinity; if it is used as
    the second value, it represents positive infinity. The range of the
    counter style is the union of all the ranges defined in the list. If
    the lower bound of any range is higher than the upper bound, the
    entire descriptor is invalid and will be ignored.

Description
-----------

The value of the range descriptor can be either auto or a comma
separated list of lower and upper bounds specified as integers.

If value is auto, then for cyclic, numeric, and fixed system, the range
will be from negative infinity to positive infinity. For alphabetic and
symbolic systems, range will be from 1 to positive infinity. For
additive systems, auto will result in the range 0 to positive infinity.
For extends systems, the range is whatever auto will produce for the
extended system.

When range is specified as integers, the value `infinite` can be used to
denote infinity. If *infinite* is specified as the first value in a
range, then it is interpreted as negative infinity. If used as upper
bound, it is taken as positive infinity.

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `auto`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
range = 
  [ [ <integer> | infinite ] ]#  |
  auto                              
```

Examples
--------

### Setting counter style over a range

[html]

```html
<ul class="list">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
  <li>Four</li>
  <li>Five</li>
  <li>Six</li>
  <li>Seven</li>
  <li>Eight</li>
  <li>Nine</li>
  <li>Ten</li>
</ul>
```

[css]

```css
@counter-style range-multi-example {
  system: cyclic;
  symbols: "\25A0" "\25A1";
  range:
    2 4,
    7 9;
}

.list {
  list-style: range-multi-example;
}
```

The above list will display as follows:

:

Specifications
--------------

  -------------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------------

  [CSS Counter Styles Level 3\
  [\#
  counter-style-range]](https://drafts.csswg.org/css-counter-styles/#counter-style-range)

  -------------------------------------------------------------------------------------------------

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

`range`

91

91

33

No

77

17

91

91

33

64

17

16.0

See also
--------

- [`list-style`](list-style.md),
    [`list-style-image`](list-style-image.md),
    [`list-style-position`](list-style-position.md)
- [`symbols()`](symbols.md), the functional notation creating anonymous
    counter styles.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/range>

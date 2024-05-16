system
======

The `system` descriptor specifies the algorithm to be used for
converting the integer value of a counter to a string representation. It
is used in a [`@counter-style`](@counter-style.md) to define the
behavior of the defined style.

If the algorithm specified in the `system` descriptor is unable to
construct the representation for a particular counter value, then that
value\'s representation will be constructed using the fallback system
provided.

Syntax
------

[css]

```css
/* Keyword values */
system: cyclic;
system: numeric;
system: alphabetic;
system: symbolic;
system: additive;
system: fixed;

/* Combined values */
system: fixed 3;
system: extends decimal;
```

This may take one of three forms:

- One of the keyword values `cyclic`, `numeric`, `alphabetic`,
    `symbolic`, `additive`, or `fixed`.
- The keyword value `fixed` along with an integer.
- The keyword value or `extends` along with a
    [`@counter-style`](@counter-style.md) name.

[`cyclic`](#cyclic)

:   Cycles through the list of symbols provided. Once the end of the
    list of symbols is reached, it will loop back to the beginning and
    start over. This system is useful for simple bullet styles with just
    one symbol, or for styles having multiple symbols. At least one
    symbol must be specified in the `symbols` descriptor, or the counter
    style is not valid.

[`fixed`](#fixed)

:   Defines a finite set of symbols are specified. Once the system has
    looped through all the specified symbols, it will fall back. This
    system is useful in cases where the counter values are finite. At
    least one symbol must be specified in the `symbols` descriptor or
    the counter style is not valid. Also an optional
    [`<integer>`](integer.md) can be specified after the system, as the
    value of the first symbol. If this integer is omitted, value of the
    first integer is taken as `1`.

[`symbolic`](#symbolic)

:   Cycles through the provided list of symbols. On each successive pass
    through the cycle, the symbols used for the counter representation
    are doubled, tripled, and so on. For example, if the original
    symbols provided were \"◽\" and \"◾\", on each successive pass, they
    will become \"◽◽\" and \"◾◾\", \"◽◽◽\" and \"◾◾◾\" and so on. At
    least one symbol must be specified in the `symbols` descriptor or
    the counter style is not valid. This counter system works for
    positive counter values only.

[`alphabetic`](#alphabetic)

:   Interprets the specified symbols as digits, to an alphabetic
    numbering system. If the characters `"a"` to `"z"` are specified as
    symbols in a counter style, with the `alphabetic` system, then the
    first 26 counter representations will be `"a"`, `"b"` up to `"z"`.
    Until this point, the behavior is the same as that of the `symbolic`
    system, described above. However, after `"z"`, it will continue as
    `"aa"`, `"ab"`, `"ac"`...

    The `symbols` descriptor must contain at least two symbols or the
    counter style is not valid. The first counter symbol provided in the
    `symbols` descriptor is interpreted as `1`, the next as `2`, and so
    on. This system is also defined strictly over positive counter
    values.

[`numeric`](#numeric)

:   Interprets the counter symbols as digits in a [place-value numbering
    system](https://en.wikipedia.org/wiki/Positional_notation). The
    numeric system is similar to the `alphabetic` system, described
    above. The main difference is that in the `alphabetic` system, the
    first counter symbol given in the `symbols` descriptor is
    interpreted as `1`, the next as `2`, and so on. However, in the
    numeric system, the first counter symbol is interpreted as 0, the
    next as `1`, then `2`, and so on.

    At least two counter symbols must be specified in the `symbols`
    descriptor or the counter style is not valid.

[`additive`](#additive)

:   Used to represent \"sign-value\" numbering systems, such as Roman
    numerals, which rather than reuse digits in different positions to
    obtain different values, define additional digits for larger values.
    The value of a number in such a system can be found out by adding
    the digits in the number.

    An additional descriptor called `additive-symbols` must be specified
    with at least one *additive tuple*, or else the counter style rule
    will not be valid. An additive tuple is similar to a composite
    counter symbol, which is made up of two parts: a normal counter
    symbol and a non-negative integer weight. The additive tuples must
    be specified in the descending order of their weights or the system
    is invalid.

[`extends`](#extends)

:   Allows authors to use the algorithm of another counter style, but
    alter its other aspects. If a counter style rule is using the
    `extends` system, any unspecified descriptors, and their values will
    be taken from the extended counter style specified. If the specified
    counter style name in extends, is not a currently defined counter
    style name, it will instead extend from the decimal counter style.

    It must not contain a `symbols` or `additive-symbols` descriptor, or
    else the counter style rule is invalid. If one or more counter
    styles definitions form a cycle with their extends values, the
    browser will treat all the participating counter styles as extending
    from the decimal style.

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `symbolic`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
system = 
  cyclic                            |
  numeric                           |
  alphabetic                        |
  symbolic                          |
  additive                          |
  [ fixed <integer>? ]              |
  [ extends <counter-style-name> ]  
```

Examples
--------

### Cyclic counter

If your browser supports it, this example will render a list like this:

```
◉ One
◉ Two
◉ Three
```

#### CSS

[css]

```css
@counter-style fisheye {
  system: cyclic;
  symbols: ◉;
  suffix: " ";
}

ul {
  list-style: fisheye;
}
```

#### Result

### Fixed counter

If your browser supports it, this example will render a list like this:

```
➀ One
➁ Two
➂ Three
4 Four
5 Five
```

#### CSS

[css]

```css
@counter-style circled-digits {
  system: fixed;
  symbols: ➀ ➁ ➂;
  suffix: " ";
}

ul {
  list-style: circled-digits;
}
```

#### Result

### Symbolic counter

If your browser supports it, this example will render a list like this:

```
  a. One
  b. Two
  c. Three
 aa. Four
 bb. Five
 cc. Six
aaa. Seven
bbb. Eight
```

#### CSS

[css]

```css
@counter-style abc {
  system: symbolic;
  symbols: a b c;
  suffix: ". ";
}

ul {
  list-style: abc;
}
```

#### Result

### Alphabetic counter

If your browser supports it, this example will render a list like this:

```
 a. One
 b. Two
 c. Three
aa. Four
ab. Five
ac. Six
ba. Seven
bb. Seven
```

#### CSS

[css]

```css
@counter-style abc {
  system: alphabetic;
  symbols: a b c;
  suffix: ". ";
}

ul {
  list-style: abc;
}
```

#### Result

### Numeric counter

If your browser supports it, this example will render a list like this:

```
 b. One
 c. Two
ba. Three
bb. Four
bc. Five
ca. Six
cb. Seven
cc. Eight
```

The first symbol provided in the `symbols` descriptor is interpreted as
`0` here.

#### CSS  

[css]

```css
@counter-style abc {
  system: numeric;
  symbols: a b c;
  suffix: ". ";
}

ul {
  list-style: abc;
}
```

#### Result

### Numeric counter with numeric symbols

As shown in the following example, if digits from `0` to `9` are
specified as symbols, this counter style will render symbols same as the
decimal counter style.

#### CSS

[css]

```css
@counter-style numbers {
  system: numeric;
  symbols: "0" "1" "2" "3" "4" "5" "6" "7" "8" "9";
  suffix: ".";
}

ul {
  list-style: numbers;
}
```

#### Result

### Additive counter

This example renders a list using Roman numerals. Notice that a `range`
is specified. This is because the representation will produce correct
Roman numerals only until the counter value of `3999`. Once outside of
the range, the rest of the counter representations will be based on the
`decimal` style, which is the fall back. If you need to represent
counter values as Roman numerals, you could use either one of the
predefined counter styles, `upper-roman` or `lower-roman`, rather than
recreating the rule yourself.

#### HTML

[html]

```html
<ul class="list">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
  <li>Four</li>
  <li>Five</li>
</ul>
```

#### CSS

[css]

```css
@counter-style upper-roman {
  system: additive;
  range: 1 3999;
  additive-symbols:
    1000 M,
    900 CM,
    500 D,
    400 CD,
    100 C,
    90 XC,
    50 L,
    40 XL,
    10 X,
    9 IX,
    5 V,
    4 IV,
    1 I;
}

ul {
  list-style: upper-roman;
}
```

#### Result

### Extends example

This example will use the algorithm, symbols, and other properties of
the `lower-alpha` counter style, but will remove the period (`'.'`)
after the counter representation, and enclose the characters in
parenthesis; like `(a)`, `(b)`, etc.

#### HTML

[html]

```html
<ul class="list">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
  <li>Four</li>
  <li>Five</li>
</ul>
```

#### CSS

[css]

```css
@counter-style alpha-modified {
  system: extends lower-alpha;
  prefix: "(";
  suffix: ") ";
}

ul {
  list-style: alpha-modified;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------------

  [CSS Counter Styles Level 3\
  [\#
  counter-style-system]](https://drafts.csswg.org/css-counter-styles/#counter-style-system)

  ---------------------------------------------------------------------------------------------------

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

`system`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/system>

additive-symbols
================

The `additive-symbols` descriptor lets you specify symbols when the
value of a `@counter-style` [`system`](system.md) descriptor is `additive`.
The `additive-symbols` descriptor defines *additive tuples*, each of
which is a pair containing a symbol and a non-negative integer weight.
The additive system is used to construct [sign-value
numbering](https://en.wikipedia.org/wiki/Sign-value_notation) systems
such as Roman numerals.

Syntax
------

[css]

```css
additive-symbols: 3 "0";
additive-symbols:
  3 "0",
  2 "\2E\20";
additive-symbols:
  3 "0",
  2 url(symbol.png);
```

When the `system` descriptor is `cyclic`, `numeric`, `alphabetic`,
`symbolic`, or `fixed`, use the [`symbols()`](symbols.md) descriptor
instead of `additive-symbols`.

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `n/a (required)`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```text
additive-symbols = 
  [ <integer [0,∞]> && <symbol> ]#  

<symbol> = 
  <string>        |
  <image>         |
  <custom-ident>  

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Specifying additive symbols

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

```css

#### CSS


[css]

```css

@counter-style additive-symbols-example {
  system: additive;
  additive-symbols:
    V 5,
    IV 4,
    I 1;
}
.list {
  list-style: additive-symbols-example;
}

```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Counter Styles Level 3\
  [\#
  counter-style-symbols]](https://drafts.csswg.org/css-counter-styles/#counter-style-symbols)

  -----------------------------------------------------------------------------------------------------

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

`additive-symbols`

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
- The [`symbols()`](symbols.md), functional notation is used for creating
    anonymous counter styles.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/additive-symbols

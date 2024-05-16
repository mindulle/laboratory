pad
===

The `pad` descriptor can be used with custom counter style definitions
when you need the marker representations to have a minimum length.

Syntax
------

[css]

```css
pad: 3 "0";
```

### Values

[`<integer> && <symbol>`](#integer_symbol)

:   The `<integer>` specifies a minimum length that all counter
    representations must reach. The value must be non-negative. If the
    minimum length is not reached, the representation will be padded
    with the specified `<symbol>`.

Description
-----------

If a marker representation is smaller than the specified pad length,
then the marker will be padded with the specified pad symbol. Marker
representations longer than the pad length are constructed as normal.
Pad descriptor takes the minimum marker length as an integer and a
symbol to be used for padding as the second parameter. A common usage of
the pad descriptor is when you need your list to start numbering from 01
and go through 02, 03 and so on, instead of just 1, 2, 3...

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `0 ""`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
pad = 
  <integer [0,∞]>  &&
  <symbol>         

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

### Padding a counter

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
@counter-style pad-example {
  system: numeric;
  symbols: "0" "1" "2" "3" "4" "5";
  pad: 2 "0";
}

.list {
  list-style: pad-example;
}
```

#### Result

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Counter Styles Level 3\
  [\#
  counter-style-pad]](https://drafts.csswg.org/css-counter-styles/#counter-style-pad)

  ---------------------------------------------------------------------------------------------

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

`pad`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/pad>

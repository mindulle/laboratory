negative
========

When defining custom counter styles, the `negative` descriptor lets you
alter the representations of negative counter values, by providing a way
to specify symbols to be appended or prepended to the counter
representation when the value is negative.

Syntax
------

[css]

```css
/* <symbol> values */
negative: "-"; /* Prepends '-' if value is negative */
negative: "(" ")"; /* Surrounds value by '(' and ')' if it is negative */
```

### Values

[first](#first) `<symbol>`

:   This symbol will be prepended to the representation when the counter
    is negative.

[second](#second) `<symbol>`

:   If present, this symbol will be appended to the representation when
    the counter is negative.

Description
-----------

If the counter value is negative, the symbol provided as value for the
descriptor is prepended to the counter representation; and a second
symbol if specified, will be appended to the representation. The
negative descriptor has effect only if the `system` value is `symbolic`,
`alphabetic`, `numeric`, `additive`, or `extends`, if the extended
counter style itself uses a negative sign. If the negative descriptor is
specified for other systems that don\'t support negative counter values,
then the descriptor is ignored.

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `"-" hyphen-minus`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
negative = 
  <symbol> <symbol>?  

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

### Rendering negative counters

#### HTML

[html]

```html
<ol class="list" start="-3">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
  <li>Four</li>
  <li>Five</li>
</ol>
```

#### CSS

[css]

```css
@counter-style neg {
  system: numeric;
  symbols: "0" "1" "2" "3" "4" "5" "6" "7" "8" "9";
  negative: "(-" ")";
}

.list {
  list-style: neg;
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

`negative`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/negative>

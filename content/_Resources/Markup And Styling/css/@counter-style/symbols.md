symbols
=======

The `symbols` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
descriptor is used to specify the symbols that the specified counter
system will use to construct counter representations.

Syntax
------

The `symbols` descriptor is specified as one or more `<symbol>`s.

### Values

[`<symbol>`](#symbol)

:   Represents a symbol used within the counter system. This must be one
    of the following data types:

    -   [`<string>`](../string)
    -   [`<image>`](../image) (Note: This value is \"at risk\" and may
        be removed from the specification. It is not yet implemented.)
    -   [`<custom-ident>`](../custom-ident)

Description
-----------

A symbol can be a string, image, or identifier. It is used within the
[`@counter-style`](@counter-style.md) [at-rule](at-rule.md).

[css]

```css
symbols: A B C D E;
symbols: "\24B6" "\24B7" "\24B8" D E;
symbols: "0" "1" "2" "4" "5" "6" "7" "8" "9";
symbols: url("one.svg") url("two.svg") url("three.svg");
symbols: indic-numbers;
```

The `symbols` descriptor must be specified when the value of the
[`system`](system.md) descriptor is `cyclic`, `numeric`, `alphabetic`,
`symbolic`, or `fixed`. When the `additive` system is used, use the
[`additive-symbols`](additive-symbols.md) descriptor instead to specify the
symbols.

While a space between quoted symbols is not required, it makes the CSS
more legible. To use a quote as a symbol, either escape the quote
character or enclose the character is using different quotes, such as
`"'"`.

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     `n/a (required)`
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
symbols = 
  <symbol>+  

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

### Setting counter symbols

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
@counter-style symbols-example {
  system: fixed;
  symbols: A "1" "\24B7" D E;
}

.list {
  list-style: symbols-example;
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

`symbols`

91Does not support `<image>` as a value for the `symbols` descriptor.

91Does not support `<image>` as a value for the `symbols` descriptor.

33Does not support `<image>` as a value for the `symbols` descriptor.

No

77Does not support `<image>` as a value for the `symbols` descriptor.

17

91Does not support `<image>` as a value for the `symbols` descriptor.

91Does not support `<image>` as a value for the `symbols` descriptor.

33Does not support `<image>` as a value for the `symbols` descriptor.

64Does not support `<image>` as a value for the `symbols` descriptor.

17

16.0Does not support `<image>` as a value for the `symbols` descriptor.

See also
--------

- The `symbols` descriptor is used within the
    [`@counter-style`](@counter-style.md) at-rule.
- [`list-style`](list-style.md),
    [`list-style-image`](list-style-image.md),
    [`list-style-position`](list-style-position.md)
- [`symbols()`](symbols.md), the functional notation creating anonymous
    counter styles
- [`url()`](url.md) function
- [CSS counter styles](css_counter_styles.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/symbols>

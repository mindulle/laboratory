suffix
======

The `suffix` descriptor of the [`@counter-style`](@counter-style.md)
rule specifies content that will be appended to the marker
representation.

Syntax
------

[css]

```css
/* <symbol> values */
suffix: "";
suffix: ") ";
suffix: url(bullet.png);
```

### Values

[`<symbol>`](#symbol)

:   Specifies a `<symbol>` that is appended to the marker
    representation. It may be a [`<string>`](string.md),
    [`<image>`](_Resources/Markup%20And%20Styling/css/image.md), or [`<custom-ident>`](custom-ident.md).

Formal definition
-----------------

  ------------------------------------- ----------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     \". \" (full stop followed by a space)
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ----------------------------------------

Formal syntax
-------------

```
suffix = 
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

### Setting a suffix for a counter

#### HTML

[html]

```html
<ul class="choices">
  <li>One</li>
  <li>Two</li>
  <li>Three</li>
  <li>None of the above</li>
</ul>
```

#### CSS

[css]

```css
@counter-style options {
  system: fixed;
  symbols: A B C D;
  suffix: ") ";
}

.choices {
  list-style: options;
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
  counter-style-suffix]](https://drafts.csswg.org/css-counter-styles/#counter-style-suffix)

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

`suffix`

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
    counter styles

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/suffix>

prefix
======

The `prefix` descriptor of the [`@counter-style`](@counter-style.md)
rule specifies content that will be prepended to the marker
representation. If not specified, the default value will be `""` (an
empty string).

Syntax
------

[css]

```css
/* <symbol> values */
prefix: "»";
prefix: "Page ";
prefix: url(bullet.png);
```

### Values

[`<symbol>`](#symbol)

:   Specifies a `<symbol>` that is prepended to the marker
    representation. It may be a [`<string>`](string.md),
    [`<image>`](_Resources/Markup%20And%20Styling/css/image.md), or [`<custom-ident>`](custom-ident.md).

Formal definition
-----------------

  ------------------------------------- ---------------------------------------
  Related [at-rule](at-rule.md)         [`@counter-style`](@counter-style.md)
  [Initial value](initial_value.md)     \"\" (the empty string)
  [Computed value](computed_value.md)   as specified
  ------------------------------------- ---------------------------------------

Formal syntax
-------------

```
prefix = 
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

### Adding a prefix to a counter

#### HTML

[html]

```html
<ul class="index">
  <li>The Boy Who Lived</li>
  <li>The Vanishing Glass</li>
  <li>The Letters from No One</li>
  <li>The Keeper of the Keys</li>
  <li>Diagon Alley</li>
</ul>
```

#### CSS

[css]

```css
@counter-style chapters {
  system: numeric;
  symbols: "0" "1" "2" "3" "4" "5" "6" "7" "8" "9";
  prefix: "Chapter ";
}

.index {
  list-style: chapters;
  padding-left: 15ch;
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
  counter-style-prefix]](https://drafts.csswg.org/css-counter-styles/#counter-style-prefix)

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

`prefix`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/prefix>

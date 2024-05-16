counter()
=========

The `counter()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) returns a string representing the current
value of the named counter, if there is one. It is generally used in the
[`content`](content.md) property of [pseudo-elements](pseudo-elements.md), but
can theoretically be used anywhere a [`<string>`](string.md) value is
supported.

Try it
------

Syntax
------

[css]

```css
/* Simple usage */
counter(countername);

/* changing the counter display */
counter(countername, upper-roman)
```

A [counter](using_css_counters.md) has no visible effect
by itself. The `counter()` function (and [`counters()`](counters.md)
function) is what makes it useful by returning developer defined strings
(or images).

### Values

[`<custom-ident>`](custom-ident.md)

:   A name identifying the counter, which is the same case-sensitive
    name used for the [`counter-reset`](counter-reset.md) and
    [`counter-increment`](counter-increment.md). The name cannot start with
    two dashes and can\'t be `none`, `unset`, `initial`, or `inherit`.

[`<counter-style>`](#counter-style)

:   A [`<list-style-type>`](list-style-type.md) name,
    [`<@counter-style>`](@counter-style.md) name or
    [`symbols()`](symbols.md) function, where a counter
    style name is a `numeric`, `alphabetic`, or `symbolic` simple
    predefined counter style, a complex longhand east Asian or Ethiopic
    predefined counter style, or other [](css_counter_styles.md). If omitted, the counter-style defaults
    to `decimal`.

### Formal syntax

```
<counter()> = 
  counter( <counter-name> , <counter-style>? )  

<counter-style> = 
  <counter-style-name>  |
  <symbols()>           

<symbols()> = 
  symbols( <symbols-type>? [ <string> | <image> ]+ )  

<symbols-type> = 
  cyclic      |
  numeric     |
  alphabetic  |
  symbolic    |
  fixed       

<image> = 
  <url>       |
  <gradient>  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### default value compared to upper Roman

#### HTML

[html]

```html
<ol>
  <li></li>
  <li></li>
  <li></li>
</ol>
```

#### CSS

[css]

```css
ol {
  counter-reset: listCounter;
}
li {
  counter-increment: listCounter;
}
li::after {
  content: "[" counter(listCounter) "] == [" counter(listCounter, upper-roman)
    "]";
}
```

#### Result

### decimal-leading-zero compared to lower-alpha

#### HTML

[html]

```html
<ol>
  <li></li>
  <li></li>
  <li></li>
</ol>
```

#### CSS

[css]

```css
ol {
  counter-reset: count;
}
li {
  counter-increment: count;
}
li::after {
  content: "[" counter(count, decimal-leading-zero) "] == [" counter(
      count,
      lower-alpha
    )
    "]";
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Lists and Counters Module Level 3\
  [\#
  counter-functions]](https://drafts.csswg.org/css-lists/#counter-functions)

  ------------------------------------------------------------------------------------

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

`counter`

1

12

1

8

9.2

3

4.4

18

4

10.1

1

1.0

See also
--------

- [Using CSS Counters](using_css_counters.md)
- [`counter-reset`](counter-reset.md)
- [`counter-set`](counter-set.md)
- [`counter-increment`](counter-increment.md)
- [`@counter-style`](@counter-style.md)
- CSS [`counters()`](counters.md) function

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/counter>

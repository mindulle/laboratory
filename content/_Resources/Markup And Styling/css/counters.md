counters()
==========

The `counters()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) enables nested counters, returning a
concatenated string representing the current values of the named
counters, if there are any. The `counters()` function has two forms:
`counters(name, string)` or `counters(name, string, style)`. It is
generally used with [pseudo-elements](pseudo-elements.md), but can be used,
theoretically, anywhere a [`<string>`](string.md) value is supported. The
generated text is the value of all counters with the given name, from
outermost to innermost, separated by the specified string. The counters
are rendered in the style indicated, defaulting to `decimal` if no style
is specified.

Try it
------

Syntax
------

[css]

```css
/* Simple usage  - style defaults to decimal */
counters(countername, '-');

/* changing the counter display */
counters(countername, '.', upper-roman)
```

A [counter](using_css_counters.md) has no visible effect
by itself. The `counters()` function (and [`counter()`](counter.md)
function) is what makes it useful by returning developer defined
content.

### Values

[`<custom-ident>`](custom-ident.md)

:   A name identifying the counters, which is the same case-sensitive
    name used for the [`counter-reset`](counter-reset.md) and
    [`counter-increment`](counter-increment.md). The name cannot start with
    two dashes and can\'t be `none`, `unset`, `initial`, or `inherit`.

[`<counter-style>`](#counter-style)

:   A counter style name or [`symbols()`](symbols.md)
    function, where a counter style name is a numeric, alphabetic, or
    symbolic simple predefined counter style, a complex longhand east
    Asian or Ethiopic predefined counter style, or other [](css_counter_styles.md). If omitted, the counter-style
    defaults to decimal

[`<string>`](string.md)

:   Any number of text characters. Non-Latin characters must be encoded
    using their Unicode escape sequences: for example, `\000A9`
    represents the copyright symbol.

### Formal syntax

```
<counters()> = 
  counters( <counter-name> , <string> , <counter-style>? )  

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
  <li>
    <ol>
      <li></li>
      <li></li>
      <li></li>
    </ol>
  </li>
  <li></li>
  <li></li>
  <li>
    <ol>
      <li></li>
      <li>
        <ol>
          <li></li>
          <li></li>
          <li></li>
        </ol>
      </li>
    </ol>
  </li>
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
li::marker {
  content: counters(listCounter, ".", upper-roman) ") ";
}
li::before {
  content: counters(listCounter, ".") " == " counters(
      listCounter,
      ".",
      lower-roman
    );
}
```

#### Result

### decimal-leading-zero compared to lower-alpha

#### HTML

[html]

```html
<ol>
  <li>
    <ol>
      <li></li>
      <li></li>
      <li></li>
    </ol>
  </li>
  <li></li>
  <li></li>
  <li>
    <ol>
      <li></li>
      <li>
        <ol>
          <li></li>
          <li></li>
          <li></li>
        </ol>
      </li>
    </ol>
  </li>
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
li::marker {
  content: counters(count, ".", upper-alpha) ") ";
}
li::before {
  content: counters(count, ".", decimal-leading-zero) " == " counters(
      count,
      ".",
      lower-alpha
    );
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

`counters`

1

12

1.5

8

10

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
- [`counter-set`](counter-set.md)
- [`counter-reset`](counter-reset.md)
- [`counter-increment`](counter-increment.md)
- [`@counter-style`](@counter-style.md)
- CSS [`counter()`](counter.md) function
- [`::marker`](::marker)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/counters>

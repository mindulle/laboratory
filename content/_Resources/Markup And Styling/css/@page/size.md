size
====

The `size` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) descriptor, used with the [`@page`](@page.md)
at-rule, defines the size and orientation of the box which is used to
represent a page. Most of the time, this size corresponds to the target
size of the printed page if applicable.

Size may either be defined with a \"scalable\" keyword (in this case the
page will fill the available dimensions) or with absolute dimensions.

Syntax
------

[css]

```css
/* Keyword values for scalable size */
size: auto;
size: portrait;
size: landscape;

/* <length> values */
/* 1 value: height = width */
size: 6in;

/* 2 values: width then height */
size: 4in 6in;

/* Keyword values for absolute size */
size: A4;
size: B5;
size: JIS-B4;
size: letter;

/* Mixing size and orientation */
size: A4 portrait;
```

### Values

[`auto`](#auto)

:   The user agent decides the size of the page. In most cases, the
    dimensions and orientation of the target sheet are used.

[`landscape`](#landscape)

:   The content of the page is displayed in landscape mode (i.e. the
    longest side of the box is horizontal).

[`portrait`](#portrait)

:   The content of the page is displayed in portrait mode (i.e. the
    longest side of the box is vertical). This is the default
    orientation.

[`<length>`](#length)

:   Any length value (see [`<length>`](length.md)). The first value
    corresponds to the width of the page box and the second one
    corresponds to its height. If only one value is provided, it is used
    for both width and height.

[`<page-size>`](#page-size)

:   A keyword which may be any of the following values:

    [A5](#a5)

    :   This matches the standard, ISO dimensions: 148mm x 210mm.

    [A4](#a4)

    :   This matches the standard, ISO dimensions: 210mm x 297mm. (most
        frequently used dimensions for personal printing.)

    [A3](#a3)

    :   This matches the standard, ISO dimensions: 297mm x 420mm.

    [B5](#b5)

    :   This matches the standard, ISO dimensions: 176mm x 250mm.

    [B4](#b4)

    :   This matches the standard, ISO dimensions: 250mm x 353mm.

    [JIS-B5](#jis-b5)

    :   This correspond to the JIS standard dimensions: 182mm x 257mm.

    [JIS-B4](#jis-b4)

    :   This correspond to the JIS standard dimensions: 257mm x 364mm.

    [letter](#letter)

    :   This keyword is an equivalent to the dimensions of letter paper
        in North America i.e. 8.5in x 11in.

    [legal](#legal)

    :   This keyword is an equivalent to the dimensions of legal papers
        in North America i.e. 8.5in x 14in.

    [ledger](#ledger)

    :   This keyword is an equivalent to the dimensions of ledger pages
        in North America i.e. 11in x 17in.

Formal definition
-----------------

  ------------------------------------- -------------------------------------------------------------------------
  Related [at-rule](at-rule.md)         [`@page`](@page.md)
  [Initial value](initial_value.md)     `auto`
  [Computed value](computed_value.md)   as specified, but with relative lengths converted into absolute lengths
  ------------------------------------- -------------------------------------------------------------------------

Formal syntax
-------------

```
size = 
  <length>                                |
  auto                                         |
  [ <page-size> || [ portrait | landscape ] ]  
```

Examples
--------

### Specifying size and orientation

[css]

```css
@page {
  size: A4 landscape;
}
```

### Specifying a custom size

[css]

```css
@page {
  size: 4in 6in;
}
```

### Nesting inside a \@media rule

[css]

```css
@media print {
  @page {
    size: 50mm 150mm;
  }
}
```

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Paged Media Module Level 3\
  [\#
  page-size-prop]](https://drafts.csswg.org/css-page/#page-size-prop)

  -----------------------------------------------------------------------------

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

`size`

15

79

95

No

15

≤13.1

37

18

95

14

≤13.4

1.5

`jis-b4`

83

83

95

No

69

No

83

83

95

59

No

13.0

`jis-b5`

83

83

95

No

69

No

83

83

95

59

No

13.0

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@page/size>

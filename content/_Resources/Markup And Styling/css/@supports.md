\@supports
==========

The `@supports` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[at-rule](at-rule.md) lets you specify CSS declarations that depend on a
browser\'s support for CSS features. Using this at-rule is commonly
called a *feature query*. The rule must be placed at the top level of
your code or nested inside any other [](at-rule.md#conditional_group_rules).

Try it
------

In JavaScript, `@supports` can be accessed via the CSS object model
interface
[`CSSSupportsRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule).

Syntax
------

The `@supports` at-rule consists of a block of statements with a
*supports condition.* The supports condition is a set of one or more
name-value pairs (e.g., `<property>: <value>`).

[css]

```css
@supports (<supports-condition>) {
  /* If the condition is true, use the CSS in this block. */
}
```

The conditions can be combined by conjunctions (`and`), disjunctions
(`or`), and/or negations (`not`).

[css]

```css
@supports (<supports-condition>) and (<supports-condition>) {
  /* If both conditions are true, use the CSS in this block. */
}
```

The precedence of operators can be defined with parentheses. Supports
conditions can use either a `<property>: <value>` declaration syntax or
a `<function()>` syntax. The following sections describe the use of each
type of supports condition.

### Declaration syntax

The declaration syntax checks if a browser supports the specified
`<property>: <value>` declaration. The declaration must be surrounded by
parentheses. The following example returns true and applies the CSS
style if the browser supports the expression `transform-origin: 5% 5%`:

[css]

```css
@supports (transform-origin: 5% 5%) {
}
```

### Function syntax

The function syntax checks if a browser supports values or expressions
within the function. The functions supported in the function syntax are
described in the following sections.

#### `selector()` [Experimental]

This function evaluates if a browser supports the specified selector
syntax. The following example returns true and applies the CSS style if
the browser supports the [child combinator](child_combinator.md):

[css]

```css
@supports selector(h2 > p) {
}
```

#### `font-tech()`

This function checks if a browser supports the specified font technology
for layout and rendering. The following example returns true and applies
the CSS style if the browser supports the `COLRv1` font technology:

[css]

```css
@supports font-tech(color-COLRv1) {
}
```

The table below describes the font technologies (`<font-tech>`),
including color font technologies (`<color-font-tech>`), font feature
technologies (`<font-features-tech>`), and other available font
technologies that can be queried using the `font-tech()` function:

  Technology               Supports
  ------------------------ -----------------------------------------------------------------------------------------------
  `<color-font-tech>`
  `color-colrv0`           Multi-colored glyphs via COLR version 0 table
  `color-colrv1`           Multi-colored glyphs via COLR version 1 table
  `color-svg`              SVG multi-colored tables
  `color-sbix`             Standard bitmap graphics tables
  `color-cbdt`             Color bitmap data tables
  `<font-features-tech>`
  `features-opentype`      OpenType `GSUB` and `GPOS` tables
  `features-aat`           TrueType `morx` and `kerx` tables
  `features-graphite`      Graphite features, namely `Silf`, `Glat` , `Gloc` , `Feat`, and `Sill` tables
  `<font-tech>`
  `incremental-patch`      Incremental font loading using the patch subset method
  `incremental-range`      Incremental font loading using the range request method
  `incremental-auto`       Incremental font loading using method negotiation
  `variations`             Font variations in TrueType and OpenType fonts to control the font axis, weight, glyphs, etc.
  `palettes`               Font palettes by means of `font-palette` to select one of many color palettes in the font

#### `font-format()`

This function checks if a browser supports the specified font format for
layout and rendering. The following example returns true and applies the
CSS style if the browser supports the `opentype` font format:

[css]

```css
@supports font-format(opentype) {
}
```

The following table describes the available formats (`<font-format>`
values) that can be queried with this function:

  Format                Description                       File extensions
  --------------------- --------------------------------- -----------------
  `collection`          OpenType Collection               `.otc`, `.ttc`
  `embedded-opentype`   Embedded OpenType                 `.eot`
  `opentype`            OpenType                          `.ttf`, `.otf`
  `svg`                 SVG Font (deprecated)             `.svg`, `.svgz`
  `truetype`            TrueType                          `.ttf`
  `woff`                WOFF 1.0 (Web Open Font Format)   `.woff`
  `woff2`               WOFF 2.0 (Web Open Font Format)   `.woff2`

### The not operator

The `not` operator precedes an expression resulting in the negation of
the expression. The following returns true if the browser\'s
[`transform-origin`](transform-origin.md) property considers
`10em 10em 10em` **to be invalid:**

[css]

```css
@supports not (transform-origin: 10em 10em 10em) {
}
```

As with any operator, the `not` operator can be applied to a declaration
of any complexity. The following examples are both valid:

[css]

```css
@supports not (not (transform-origin: 2px)) {
}
@supports (display: grid) and (not (display: inline-grid)) {
}
```

**Note:** There is no need to enclose the `not` operator between two
parentheses at the top level. To combine it with other operators, like
`and` and `or`, the parentheses are required.

### The and operator

The `and` operator creates a new expression from the conjunction of two
shorter expressions. It returns true only if **both** of the shorter
expressions are also true. The following example returns true if and
only if the two shorter expressions are simultaneously true:

[css]

```css
@supports (display: table-cell) and (display: list-item) {
}
```

Multiple conjunctions can be juxtaposed without the need of more
parentheses. The following are both equivalent:

[css]

```css
@supports (display: table-cell) and (display: list-item) and (display: contents) {
}
@supports (display: table-cell) and
  ((display: list-item) and (display: contents)) {
}
```

### The or operator

The `or` operator creates a new expression from the disjunction of two
shorter expressions. It returns true if **one or both** of the shorter
expressions is also true. The following example returns true if at least
one of the two shorter expressions is true:

[css]

```css
@supports (transform-style: preserve) or (-moz-transform-style: preserve) {
}
```

Multiple disjunctions can be juxtaposed without the need of more
parentheses. The following are both equivalent:

[css]

```css
@supports (transform-style: preserve) or (-moz-transform-style: preserve) or (-webkit-transform-style: preserve) {}

@supports (transform-style: preserve-3d) or ((-moz-transform-style: preserve-3d) or (-webkit-transform-style: preserve-3d))) {}
```

**Note:** When using both `and` and `or` operators, the parentheses must
be used to define the order in which they apply. Otherwise, the
condition is invalid and the whole rule is ignored.

Formal syntax
-------------

```
@supports = 
  @supports <supports-condition>   

<supports-condition> = 
  not <supports-in-parens>                            |
  <supports-in-parens> [ and <supports-in-parens> ]*  |
  <supports-in-parens> [ or <supports-in-parens> ]*   

<supports-in-parens> = 
  ( <supports-condition> )  |
  <supports-feature>        |
  <general-enclosed>        

<supports-feature> = 
  <supports-decl>  

<general-enclosed> = 
  [ <function-token> <any-value>? ) ]  |
  [ ( <any-value>? ) ]                 

<supports-decl> = 
  ( <declaration> )  
```

Examples
--------

### Testing for the support of a CSS property

[css]

```css
@supports (animation-name: test) {
  /* CSS applied when animations are supported without a prefix */
  @keyframes {
    /* Other at-rules can be nested inside */
  }
}
```

### Testing for the support of a given CSS property or a prefixed version

[css]

```css
@supports (text-stroke: 10px) or (-webkit-text-stroke: 10px) {
  /* CSS applied when text-stroke, prefixed or not, is supported */
}
```

### Testing for the non-support of a specific CSS property

[css]

```css
@supports not ((text-align-last: justify) or (-moz-text-align-last: justify)) {
  /* CSS to provide fallback alternative for text-align-last: justify */
}
```

### Testing for the support of a selector

CSS conditional rules provide the ability to test for the support of a
selector such as [`:has()`](:has).

[css]

```css
/* This rule won't be applied in browsers that don't support :has() */
ul:has(> li li) {
  /* CSS is applied when the :has(…) pseudo-class is supported */
}

@supports not selector(:has(a, b)) {
  /* Fallback for when :has() is unsupported */
  ul > li,
  ol > li {
    /* The above expanded for browsers that don't support :has(…) */
  }
}

/* Note: So far, there's no browser that supports the `of` argument of :nth-child(…) */
@supports selector(:nth-child(1n of a, b)) {
  /* This rule needs to be inside the @supports block, otherwise
     it will be partially applied in browsers which don't support
     the `of` argument of :nth-child(…) */
  :is(:nth-child(1n of ul, ol) a, details > summary) {
    /* CSS applied when the :is(…) selector and
       the `of` argument of :nth-child(…) are both supported */
  }
}
```

### Testing for the support of a font technology

The following example applies the CSS style if the browser supports the
`COLRv1` font technology:

[css]

```css
@import url("https://fonts.googleapis.com/css2?family=Bungee+Spice");

@supports font-tech(color-COLRv1) {
  font-family: "Bungee Spice";
}
```

It\'s also possible to test for the support of a font technology by
using the `tech` function inside the [`@font-face`](@font-face.md) at-rule.
If a browser doesn\'t support the font technology, a fallback font
(`Bungee-fallback.otf`) can be used instead.

[css]

```css
@font-face {
  font-family: "Bungee Spice";
  src:
    url("https://fonts.googleapis.com/css2?family=Bungee+Spice") tech(color-COLRv1),
    url("Bungee-fallback.otf") format("opentype");
}
```

### Testing for the support of a font format

The following example applies the CSS style if the browser supports the
`woff2` font format:

[css]

```css
@supports font-format(woff2) {
  font-family: "Open Sans";
  src: url("open-sans.woff2") format("woff2");
}
```

Specifications
--------------

  ----------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------

  [CSS Conditional Rules Module Level 4\
  [\#
  at-supports-ext]](https://drafts.csswg.org/css-conditional-4/#at-supports-ext)

[CSS Conditional Rules Module Level 3\
  [\# at-supports]](https://drafts.csswg.org/css-conditional-3/#at-supports)
  ----------------------------------------------------------------------------------------

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

`@supports`

28

12

22

No

12.1

9

4.4

28

22

12.1

9

1.5

`font-format`

No

No

106

No

No

17

No

No

106

No

17

No

`font-tech`

No

No

106

No

No

17

No

No

106

No

17

No

`selector`

83

83

69

No

69

14.1

83

83

79

No

14.5

13.0

See also
--------

- [Using feature queries](using_feature_queries.md)
- The CSSOM class
    [`CSSSupportsRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSSupportsRule),
    and the
    [`CSS.supports()`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/supports_static)
    method that allows the same check to be performed via JavaScript.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/@supports>

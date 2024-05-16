line-height
===========

The `line-height`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the height of a line box. It\'s commonly used to set the distance
between lines of text. On block-level elements, it specifies the minimum
height of line boxes within the element. On
non-[replaced](replaced_element.md) inline elements, it specifies the
height that is used to calculate line box height.

Try it
------

Syntax
------

[css]

```css
/* Keyword value */
line-height: normal;

/* Unitless values: use this number multiplied
by the element's font size */
line-height: 3.5;

/* <length> values */
line-height: 3em;

/* <percentage> values */
line-height: 34%;

/* Global values */
line-height: inherit;
line-height: initial;
line-height: revert;
line-height: revert-layer;
line-height: unset;
```

The `line-height` property is specified as any one of the following:

- a `<number>`
- a `<length>`
- a `<percentage>`
- the keyword `normal`.

### Values

[`normal`](#normal)

:   Depends on the user agent. Desktop browsers (including Firefox) use
    a default value of roughly `1.2`, depending on the element\'s
    `font-family`.

[`<number>`](#number) (unitless)

:   The used value is this unitless [`<number>`](number.md) multiplied by
    the element\'s own font size. The computed value is the same as the
    specified `<number>`. In most cases, **this is the preferred way**
    to set `line-height` and avoid unexpected results due to
    inheritance.

[`<length>`](#length)

:   The specified [`<length>`](length.md) is used in the calculation of the
    line box height. Values given in **em** units may produce unexpected
    results (see example below).

[`<percentage>`](#percentage)

:   Relative to the font size of the element itself. The computed value
    is this [`<percentage>`](percentage.md) multiplied by the element\'s
    computed font size. **Percentage** values may produce unexpected
    results (see the second example below).

Accessibility concerns
----------------------

Use a minimum value of `1.5` for `line-height` for main paragraph
content. This will help people experiencing low vision conditions, as
well as people with cognitive concerns such as Dyslexia. If the page is
zoomed to increase the text size, using a unitless value ensures that
the line height will scale proportionately.

[W3C Understanding WCAG
2.1](https://www.w3.org/TR/WCAG21/#visual-presentation)

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  Percentages                        refer to the font size of the element itself
  [Computed value](computed_value.md)   for percentage and length values, the absolute length, otherwise as specified
  Animation type                     either number or length
  ---------------------------------- ---------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
line-height = 
  normal               |
  <number>             |
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Basic example

[css]

```css
/* All rules below have the same resultant line height */

/* number/unitless */
div {
  line-height: 1.2;
  font-size: 10pt;
}

/* length */
div {
  line-height: 1.2em;
  font-size: 10pt;
}

/* percentage */
div {
  line-height: 120%;
  font-size: 10pt;
}

/* font shorthand */
div {
  font:
    10pt/1.2 Georgia,
    "Bitstream Charter",
    serif;
}
```

It is often more convenient to set `line-height` by using the
[`font`](font.md) shorthand as shown above, but this requires the
`font-family` property to be specified as well.

### Prefer unitless numbers for line-height values

This example shows why it is better to use [`<number>`](number.md) values
instead of [`<length>`](length.md) values. We will use two
[`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
elements. The first, with the green border, uses a unitless
`line-height` value. The second, with the red border, uses a
`line-height` value defined in `em`s.

#### HTML

[html]

```html
<div class="box green">
  <h1>Avoid unexpected results by using unitless line-height.</h1>
  Length and percentage line-heights have poor inheritance behavior.
</div>

<div class="box red">
  <h1>Avoid unexpected results by using unitless line-height.</h1>
  Length and percentage line-heights have poor inheritance behavior
</div>

<!-- The first <h1> line-height is calculated from its own font-size   (30px × 1.1) = 33px -->
<!-- The second <h1> line-height results from the red div's font-size  (15px × 1.1) = 16.5px, probably not what you want -->
```

#### CSS

[css]

```css
.green {
  line-height: 1.1;
  border: solid limegreen;
}

.red {
  line-height: 1.1em;
  border: solid red;
}

h1 {
  font-size: 30px;
}

.box {
  width: 18em;
  display: inline-block;
  vertical-align: top;
  font-size: 15px;
}
```

#### Result

Specifications
--------------

  -------------------------------------------------------------------------------------------

Specification
  -------------------------------------------------------------------------------------------

  [CSS Inline Layout Module Level 3\
  [\#
  line-height-property]](https://drafts.csswg.org/css-inline/#line-height-property)

  -------------------------------------------------------------------------------------------

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

`line-height`

1

12

1

4

7

1

4.4

18

4

10.1

1

1.0

See also
--------

- [`font`](font.md), [`font-size`](font-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/line-height>

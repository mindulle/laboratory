calc()
======

The `calc()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) lets you perform calculations when specifying
CSS property values. It can be used with [`<length>`](length.md),
[`<frequency>`](frequency.md), [`<angle>`](angle.md), [`<time>`](time.md),
[`<percentage>`](percentage.md), [`<number>`](number.md), or
[`<integer>`](integer.md) values.

Try it
------

Syntax
------

[css]

```css
/* property: calc(expression) */
width: calc(100% - 80px);
```

The `calc()` function takes a single expression as its parameter, with
the expression\'s result used as the value. The expression can be any
simple expression combining the following operators, using standard
[operator precedence
rules](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Math#operator_precedence):

[`+`](#sect1)

:   Addition.

[`-`](#-)

:   Subtraction.

[`*`](#sect2)

:   Multiplication. At least one of the arguments must be a
    [`<number>`](number.md).

[`/`](#sect3)

:   Division. The right-hand side must be a [`<number>`](number.md).

The operands in the expression may be any [`<length>`](length.md) syntax
value. You can use different units for each value in your expression, if
you wish. You may also use parentheses to establish computation order
when needed.

### Notes

Serializing the arguments inside `calc()` follows the IEEE-754 standard
for floating point math which means there\'s a few cases to be aware of
regarding the `infinity` and `NaN` constants. For more details on how
constants are serialized, see the [`calc-constant`](calc-constant.md) page.

In addition, the following notes apply:

- The `+` and `-` operators **must be surrounded by
    [whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace)**.
    For instance, `calc(50% -8px)` will be parsed as \"a percentage
    followed by a negative length\" --- which is an invalid expression
    --- while `calc(50% - 8px)` is \"a percentage followed by a
    subtraction operator and a length\". Likewise, `calc(8px + -50%)` is
    treated as \"a length followed by an addition operator and a
    negative percentage\".
- The `*` and `/` operators do not require whitespace, but adding it
    for consistency is recommended.
- Math expressions involving percentages for widths and heights on
    table columns, table column groups, table rows, table row groups,
    and table cells in both auto and fixed layout tables *may* be
    treated as if `auto` had been specified.
- It is permitted to nest `calc()` functions, in which case the inner
    ones are treated as simple parentheses.
- For lengths, you can\'t use `0` to mean `0px` (or another length
    unit); instead, you must use the version with the unit:
    `margin-top: calc(0px + 20px);` is valid, while
    `margin-top: calc(0 + 20px);` is invalid.
- The `calc()` function cannot directly substitute the numeric value
    for percentage types; for instance `calc(100 / 4)%` is invalid,
    while `calc(100% / 4)` is valid.

### Formal syntax

```
<calc()> = 
  calc( <calc-sum> )  

<calc-sum> = 
  <calc-product> [ [ '+' | '-' ] <calc-product> ]*  

<calc-product> = 
  <calc-value> [ [ '*' | '/' ] <calc-value> ]*  

<calc-value> = 
  <number>         |
  <dimension>      |
  <percentage>     |
  <calc-constant>  |
  ( <calc-sum> )   

<calc-constant> = 
  e          |
  pi         |
  infinity   |
  -infinity  |
  NaN        
```

Accessibility concerns
----------------------

When `calc()` is used for controlling text size, be sure that one of the
values includes a [relative length unit](length.md#relative_length_units),
for example:

[css]

```css
h1 {
  font-size: calc(1.5rem + 3vw);
}
```

This ensures that text size will scale if the page is zoomed.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

Usage with integers
-------------------

When `calc()` is used where an [`<integer>`](integer.md) is expected, the
value will be rounded to the nearest integer. For example:

[css]

```css
.modal {
  z-index: calc(3 / 2);
}
```

This will give `.modal` a final `z-index` value of 2.

Examples
--------

### Positioning an object on screen with a margin

`calc()` makes it easy to position an object with a set margin. In this
example, the CSS creates a banner that stretches across the window, with
a 40-pixel gap between both sides of the banner and the edges of the
window:

[css]

```css
.banner {
  position: absolute;
  left: 40px;
  width: calc(100% - 80px);
  border: solid black 1px;
  box-shadow: 1px 2px;
  background-color: yellow;
  padding: 6px;
  text-align: center;
  box-sizing: border-box;
}
```

[html]

```html
<div class="banner">This is a banner!</div>
```

### Automatically sizing form fields to fit their container

Another use case for `calc()` is to help ensure that form fields fit in
the available space, without extruding past the edge of their container,
while maintaining an appropriate margin.

Let\'s look at some CSS:

[css]

```css
input {
  padding: 2px;
  display: block;
  width: calc(100% - 1em);
}

#form-box {
  width: calc(100% / 6);
  border: 1px solid black;
  padding: 4px;
}
```

Here, the form itself is established to use 1/6 of the available window
width. Then, to ensure that input fields retain an appropriate size, we
use `calc()` again to establish that they should be the width of their
container minus 1em. Then, the following HTML makes use of this CSS:

[html]

```html
<form>
  <div id="form-box">
    <label for="misc">Type something:</label>
    <input type="text" id="misc" name="misc" />
  </div>
</form>
```

### Nested `calc()` with CSS Variables

You can also use `calc()` with [CSS variables](css_cascading_variables.md).
Consider the following code:

[css]

```css
.foo {
  --widthA: 100px;
  --widthB: calc(var(--widthA) / 2);
  --widthC: calc(var(--widthB) / 2);
  width: var(--widthC);
}
```

After all variables are expanded, `widthC`\'s value will be
`calc(calc(100px / 2) / 2)`, then when it\'s assigned to `.foo`\'s width
property, all inner `calc()`s (no matter how deeply nested) will be
flattened to just parentheses, so the `width` property\'s value will be
eventually `calc((100px / 2) / 2)`, i.e. `25px`. In short: a `calc()`
inside of a `calc()` is identical to just parentheses.

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# calc-func]](https://drafts.csswg.org/css-values/#calc-func)

  -----------------------------------------------------------------------

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

`calc`

2619

12

16\[\"Before Firefox 59 `calc()` is not supported in `rgb()` and other
color functions.\", \"Before Firefox 57 `calc(1*2*3)` is not parsed
successfully.\", \"Firefox 57 increased the number of places `calc()`
could substitute another value. See [bug
1350857](https://bugzil.la/1350857).\"\]

4--53

9

15

76

≤37≤37

28

16\[\"Before Firefox 59 `calc()` is not supported in `rgb()` and other
color functions.\", \"Before Firefox 57 `calc(1*2*3)` is not parsed
successfully.\", \"Firefox 57 increased the number of places `calc()`
could substitute another value. See [bug
1350857](https://bugzil.la/1350857).\"\]

4--53

14

76

1.5

`gradient_color_stops`

19

12

19

9

15

6

37

28

19

15

6

1.5

`nested`

51

16

48

No

38

11

51

51

48

41

11

5.0

`number_values`

31

12

48

9

18

6

4.4.3

31

48

18

6

2.0

See also
--------

- [`<calc-constant>`](calc-constant.md)
- [CSS functions](css_functions.md)
- [A Complete Guide to calc() in
    CSS](https://css-tricks.com/a-complete-guide-to-calc-in-css/)
    (CSS-Tricks)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/calc>

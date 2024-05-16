clamp()
=======

The `clamp()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[function](css_functions.md) clamps a middle value within a range of values
between a defined minimum bound and a maximum bound. The function takes
three parameters: a minimum value, a preferred value, and a maximum
allowed value.

Try it
------

Note that using `clamp()` for font sizes, as in these examples, allows
you to set a font-size that grows with the size of the viewport, but
doesn\'t go below a minimum font-size or above a maximum font-size. It
has the same effect as the code in [Fluid
Typography](https://css-tricks.com/snippets/css/fluid-typography/) but
in one line, and without the use of media queries.

Syntax
------

[css]

```css
/* Static values */
width: clamp(200px, 40%, 400px);
width: clamp(20rem, 30vw, 70rem);
width: clamp(10vw, 20em, 100vw);

/* Calculated values */
width: clamp(min(10vw, 20rem), 300px, max(90vw, 55rem));
width: clamp(100px, calc(30% / 2rem + 10px), 900px);
```

### Parameters

The `clamp(min, val, max)` function accepts three comma-separated
expressions as its parameters.

[`min`](#min)

:   The minimum value is the smallest (most negative) value. This is the
    lower bound in the range of allowed values. If the preferred value
    is less than this value, the minimum value will be used.

[`val`](#val)

:   The preferred value is the expression whose value will be used as
    long as the result is between the minimum and maximum values.

[`max`](#max)

:   The maximum value is the largest (most positive) expression value to
    which the value of the property will be assigned if the preferred
    value is greater than this upper bound.

The expressions can be math functions (see [`calc()`](calc.md) for more
information), literal values, other expressions that evaluate to a valid
argument type (like [`<length>`](length.md)), or nested [`min()`](min.md) and
[`max()`](max.md) functions. For math expressions, you can use addition,
subtraction, multiplication, and division without using the `calc()`
function itself. You may also use parentheses to establish computation
order when needed.

You can use different units for each value in your expressions and
different units in any math function making up any of the arguments.

Keep the following aspects in mind while working with the function:

- Math expressions involving percentages for widths and heights on
    table columns, table column groups, table rows, table row groups,
    and table cells in both auto and fixed layout tables *may* be
    treated as if `auto` had been specified.
- It is permitted to nest `max()` and `min()` functions as expression
    values, in which case the inner ones are treated as simple
    parentheses. The expressions are full math expressions, so you can
    use direct addition, subtraction, multiplication and division
    without using the calc() function itself.
- The expression can be values combining the addition ( `+` ),
    subtraction ( `-` ), multiplication ( `*` ) and division ( `/` )
    operators, using standard operator precedence rules. Make sure to
    put a space on each side of the `+` and `-` operands. The operands
    in the expression may be any [`<length>`](length.md) syntax value. You
    can use different units for each value in your expression. You may
    also use parentheses to establish computation order when needed.
- Oftentimes you will want to use [`min()`](min.md) and [`max()`](max.md)
    within a `clamp()` function.

### Return value

`clamp(MIN, VAL, MAX)` is resolved as `max`(MIN, [`min`](min.md)(VAL,
MAX)).

Based on the provided parameters, the function returns
[`<length>`](length.md), [`<frequency>`](frequency.md), [`<angle>`](angle.md),
[`<time>`](time.md), [`<percentage>`](percentage.md), [`<number>`](number.md), or
[`<integer>`](integer.md).

### Formal syntax

```
<clamp()> = 
  clamp( <calc-sum># )  

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

Examples
--------

### min(), max(), and clamp() comparison

In this example we have a web page that uses [`min()`](min.md),
[`max()`](max.md), and [`clamp()`](clamp.md) to set sizes responsively.

The example adjusts the sizes of page elements in three ways:

- the lengths of the lines of text
- the font size of paragraph text
- the font size of heading text

In all three cases, the page uses a combination of a viewport-relative
units ([`vw`](length.md#vw) and [`<percentage>`](percentage.md)), to set a
size that varies with the viewport width, and a value that is not
viewport relative ([`rem`](length.md#rem) and [`px`](length.md#px)) to
implement minimum and/or maximum sizes.

The example is at https://mdn.github.io/css-examples/min-max-clamp/>.
Open it in a new window and try adjusting the window width.

The **line length** (controlled by the [`width`](_Resources/Markup%20And%20Styling/css/width.md) of the
[`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)
element) will increase as the window width increases, but only up to a
certain point (`1000px`), and beyond that point, it won\'t increase
anymore. We\'re using `min()` to set a **maximum line length**: it can
go under `1000px`, but won\'t go over. This is helpful because long
lines are harder to read, so we often want to limit how long a line can
be. To achieve this we use `min(1000px, calc(70% + 100px))`: when the
result of the percentage-based calculation goes above `1000px`, we
switch to the fixed `1000px` value.

The **size of the paragraph text**, controlled by the
[`font-size`](font-size.md) of the
[`<p>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
element, decreases as the window gets narrower, but only up to a certain
point, and beyond that point (the point where `1.2vw` is less than
`1.2rem`) it doesn\'t get any smaller: it stays at `1.2rem`. We\'re
using `max()` to set a **minimum font size**: the font can grow above
`1.2rem` but will never go below it. This is helpful because really
small text is hard to read. To achieve this we use `max(1.2rem, 1.2vw)`.
This means that the `font-size` will be set at `1.2rem`, unless the
computed value of `1.2vw` is greater than that of `1.2rem`, in which
case it will be set to `1.2vw` instead.

The **size of the heading text**, controlled by the
[`font-size`](font-size.md) of the
[`<h1>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
element, has a viewport-relative value with both a maximum and a minimum
threshold. To achieve this we use `clamp(1.8rem, 2.5vw, 2.8rem)`. The
viewport-relative value is `2.5vw` but it is clamped between `1.8rem`
and `2.8rem`, so:

- if the calculated value of `2.5vw` is less than `1.8rem`, then
    `1.8rem` will be used
- if the calculated value of `2.5vw` is greater than `2.8rem`, then
    `2.8rem` will be used.

This prevents the heading text from getting too small in a very narrow
window, or too big in a very wide window.

#### HTML

[html]

```html
<h1>Simple responsive test</h1>
<p>
  Lorem ipsum dolor sit amet, consectetur adipiscing elit. In orci orci,
  eleifend id risus nec, mattis rutrum velit. Suspendisse fringilla egestas erat
  eu convallis. Phasellus eu velit ut magna dapibus elementum cursus at ligula.
  Ut tempus varius nibh, nec auctor sapien iaculis sit amet. Fusce iaculis,
  libero quis elementum viverra, nulla ante accumsan lectus, sit amet convallis
  lacus ipsum vel est. Curabitur et urna non est consectetur pulvinar vel id
  risus. Ut vestibulum, sem in semper aliquet, felis arcu euismod sapien, ac
  imperdiet massa nisl quis sem. Vestibulum ac elementum felis, in tempor velit.
  Pellentesque purus ex, mattis at ornare quis, porta condimentum mi. Donec
  vestibulum ligula vel nulla blandit, quis euismod nulla vestibulum.
  Suspendisse potenti. Nunc neque mauris, tempor sed facilisis at, ultrices eget
  nulla. Pellentesque convallis ante nec augue porttitor, id tempus ante luctus.
</p>

<p>
  Integer rutrum sollicitudin tellus, quis cursus nulla scelerisque nec. Nunc eu
  facilisis lorem. Maecenas faucibus sapien eleifend, semper tellus at, pharetra
  quam. Cras feugiat vulputate tortor at rhoncus. Class aptent taciti sociosqu
  ad litora torquent per conubia nostra, per inceptos himenaeos. Nam non felis
  quis sem lobortis sodales vel id libero. Phasellus sit amet placerat lorem.
</p>
```

#### CSS

[css]

```css
html {
  font-family: sans-serif;
}

body {
  margin: 0 auto;
  width: min(1000px, calc(70% + 100px));
}

h1 {
  letter-spacing: 2px;
  font-size: clamp(1.8rem, 2.5vw, 2.8rem);
}

p {
  line-height: 1.5;
  font-size: max(1.2rem, 1.2vw);
}
```

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\#
  calc-notation]](https://drafts.csswg.org/css-values/#calc-notation)

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

`clamp`

79

79

75

No

66

13.1

79

79

79

57

13.4

12.0

See also
--------

- [`calc()`](calc.md)
- [`max()`](max.md)
- [`min()`](min.md)
- [CSS
    Values](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/clamp>

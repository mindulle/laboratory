font-weight
===========

The `font-weight`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the weight (or boldness) of the font. The weights available depend on
the [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md) that is currently set.

Try it
------

Syntax
------

[css]

```css
/* <font-weight-absolute> keyword values */
font-weight: normal;
font-weight: bold;

/* <font-weight-absolute> numeric values [1,1000] */
font-weight: 100;
font-weight: 200;
font-weight: 300;
font-weight: 400; /* normal */
font-weight: 500;
font-weight: 600;
font-weight: 700; /* bold */
font-weight: 800;
font-weight: 900;

/* Keyword values relative to the parent */
font-weight: lighter;
font-weight: bolder;

/* Global values */
font-weight: inherit;
font-weight: initial;
font-weight: revert;
font-weight: revert-layer;
font-weight: unset;
```

The `font-weight` property is specified using either a
`<font-weight-absolute>` value or a relative weight value, as listed
below.

### Values

[`normal`](#normal)

:   Normal font weight. Same as `400`.

[`bold`](#bold)

:   Bold font weight. Same as `700`.

[`<number>`](#number)

:   A [`<number>`](number.md) value between 1 and 1000, both values
    included. Higher numbers represent weights that are bolder than (or
    as bold as) lower numbers. This allows fine-grain control for
    [variable fonts](#variable_fonts). For non-variable fonts, if the
    exact specified weight is unavailable, a [fallback
    weight](#fallback-weights) algorithm is used --- numeric values that
    are divisible by 100 correspond to common weight names, as described
    in the [Common weight name mapping](#common_weight_name_mapping)
    section below.

[`lighter`](#lighter)

:   One relative font weight lighter than the parent element. Note that
    only four font weights are considered for relative weight
    calculation; see the [Meaning of relative
    weights](#meaning_of_relative_weights) section below.

[`bolder`](#bolder)

:   One relative font weight heavier than the parent element. Note that
    only four font weights are considered for relative weight
    calculation; see the [Meaning of relative
    weights](#meaning_of_relative_weights) section below.

### Fallback weights

If the exact weight given is unavailable, then the following rule is
used to determine the weight actually rendered:

- If the target weight given is between `400` and `500` inclusive:
  - Look for available weights between the target and `500`, in
        ascending order.
  - If no match is found, look for available weights less than the
        target, in descending order.
  - If no match is found, look for available weights greater than
        `500`, in ascending order.
- If a weight less than `400` is given, look for available weights
    less than the target, in descending order. If no match is found,
    look for available weights greater than the target, in ascending
    order.
- If a weight greater than `500` is given, look for available weights
    greater than the target, in ascending order. If no match is found,
    look for available weights less than the target, in descending
    order.

### Meaning of relative weights

When `lighter` or `bolder` is specified, the below chart shows how the
absolute font weight of the element is determined.

Note that when using relative weights, only four font weights are
considered --- thin (100), normal (400), bold (700), and heavy (900). If
a font family has more weights available, they are ignored for the
purposes of relative weight calculation.

  Inherited value   `bolder`   `lighter`
  ----------------- ---------- -----------
  100               400        100
  200               400        100
  300               400        100
  400               700        100
  500               700        100
  600               900        400
  700               900        400
  800               900        700
  900               900        700

### Common weight name mapping

The numerical values `100` to `900` roughly correspond to the following
common weight names (see the [OpenType
specification](https://docs.microsoft.com/typography/opentype/spec/os2#usweightclass)):

  Value   Common weight name
  ------- -----------------------------------------------------------------------------------------------------------------------------
  100     Thin (Hairline)
  200     Extra Light (Ultra Light)
  300     Light
  400     Normal (Regular)
  500     Medium
  600     Semi Bold (Demi Bold)
  700     Bold
  800     Extra Bold (Ultra Bold)
  900     Black (Heavy)
  950     [Extra Black (Ultra Black)](https://docs.microsoft.com/dotnet/api/system.windows.fontweights?view=netframework-4.8#remarks)

### Variable fonts

While many fonts have a particular weight corresponding to one of the
numbers in [Common weight name mapping](#common_weight_name_mapping),
most variable fonts support a range of weights providing much finer
granularity, giving designers and developers more control over the
chosen weight.

For TrueType or OpenType variable fonts, the \"wght\" variation is used
to implement varying widths.

This demo loads with `font-weight: 500;` set. Change the value of the
`font-weight` property to see the weight of the text change.

Accessibility concerns
----------------------

People experiencing low vision conditions may have difficulty reading
text set with a `font-weight` value of `100` (Thin/Hairline) or `200`
(Extra Light), especially if the font has a [](_Resources/Markup%20And%20Styling/css/color.md#accessibility_concerns).

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

Formal definition
-----------------

  ---------------------------------- ------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         all elements. It also applies to [`::first-letter`](::first-letter) and [`::first-line`](::first-line).
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   the keyword or the numerical value as specified, with `bolder` and `lighter` transformed to the real value
  Animation type                     a [font weight](_Resources/Markup%20And%20Styling/css/font-weight.md#interpolation)
  ---------------------------------- ------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
font-weight = 
  <font-weight-absolute>  |
  bolder                  |
  lighter                 

<font-weight-absolute> = 
  normal             |
  bold               |
  <number [1,1000]>  
```

Examples
--------

### Setting font weights

#### HTML

[html]

```html
<p>
  Alice was beginning to get very tired of sitting by her sister on the bank,
  and of having nothing to do: once or twice she had peeped into the book her
  sister was reading, but it had no pictures or conversations in it, "and what
  is the use of a book," thought Alice "without pictures or conversations?"
</p>

<div>
  I'm heavy<br />
  <span>I'm lighter</span>
</div>
```

#### CSS

[css]

```css
/* Set paragraph text to be bold. */
p {
  font-weight: bold;
}

/* Set div text to two steps heavier than
   normal but less than a standard bold. */
div {
  font-weight: 600;
}

/* Set span text to be one step lighter
   than its parent. */
span {
  font-weight: lighter;
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Fonts Module Level 4\
  [\#
  font-weight-prop]](https://drafts.csswg.org/css-fonts/#font-weight-prop)

  ----------------------------------------------------------------------------------

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

`font-weight`

2

12

1

3

3.5

1

4.4

18

4

10.1

1

1.0

`number`

62

17

61

No

49

11

62

62

61

46

11

8.0

See also
--------

- [`font-family`](_Resources/Markup%20And%20Styling/css/font-family.md)
- [`font-style`](_Resources/Markup%20And%20Styling/css/font-style.md)
- [Fundamental text and font
    styling](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text/Fundamentals)
- [CSS fonts](css_fonts.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/font-weight>

text-combine-upright
====================

The `text-combine-upright`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the combination of characters into the space of a single character. If
the combined text is wider than 1em, the user agent must fit the
contents within 1em. The resulting composition is treated as a single
upright glyph for layout and decoration. This property only has an
effect in vertical writing modes.

This is used to produce an effect that is known as tate-chū-yoko
"縦中横" in Japanese, or as "橫向文字" in Chinese.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
text-combine-upright: none;
text-combine-upright: all;

/* Digits values */
text-combine-upright: digits; /* fits 2 consecutive digits horizontally inside vertical text */
text-combine-upright: digits 4; /* fits up to 4 consecutive digits horizontally inside vertical text */

/* Global values */
text-combine-upright: inherit;
text-combine-upright: initial;
text-combine-upright: revert;
text-combine-upright: revert-layer;
text-combine-upright: unset;
```

### Values

[`none`](#none)

:   There is no special processing.

[`all`](#all)

:   Attempts to typeset all consecutive characters within the box
    horizontally, such that they take up the space of a single character
    within the vertical line of the box.

[`digits <integer>?`](#digits_integer)

:   Attempts to display a sequence of consecutive
    [ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
    digits (U+0030--U+0039) that has as many or fewer characters than
    the specified integer, such that it takes up the space of a single
    character within the vertical line box. If the integer is omitted,
    it computes to 2. Integers outside the range of 2-4 are invalid.

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         non-replaced inline elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   specified keyword, plus integer if \'digits\'
  Animation type                     Not animatable
  ---------------------------------- -----------------------------------------------

Formal syntax
-------------

```
text-combine-upright = 
  none                         |
  all                          |
  [ digits <integer [2,4]>? ]  
```

Examples
--------

### Using \'all\' with horizontal text

The all value requires markup around every piece of horizontal text, but
it is currently supported by more browsers than the digits value.

#### HTML

[html]

```html
<p lang="zh-Hant">
  民國<span class="num">105</span>年<span class="num">4</span>月<span
    class="num"
    >29</span
  >日
</p>
```

#### CSS

[css]

```css
html {
  writing-mode: vertical-rl;
  font: 24px serif;
}
.num {
  text-combine-upright: all;
}
```

#### Results

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [CSS Writing Modes Level 4\
  [\#
  text-combine-upright]](https://drafts.csswg.org/css-writing-modes/#text-combine-upright)

  --------------------------------------------------------------------------------------------------

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

`text-combine-upright`

48

9This property was initially named `-webkit-text-combine` according to a
[2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

7912--79

48Before version 81, Firefox implemented the property as animatable.
This was corrected to spec in 81.

11

35

15This property was initially named `-webkit-text-combine` according to
a [2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

15.4

5.1This property was initially named `-webkit-text-combine` according to
a [2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

48

≤37This property was initially named `-webkit-text-combine` according to
a [2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

48

18This property was initially named `-webkit-text-combine` according to
a [2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

48Before version 81, Firefox implemented the property as animatable.
This was corrected to spec in 81.

35

14This property was initially named `-webkit-text-combine` according to
a [2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

15.4

5This property was initially named `-webkit-text-combine` according to a
[2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

5.0

1.0This property was initially named `-webkit-text-combine` according to
a [2011 version of the CSS3 Writing Modes
specification](https://www.w3.org/TR/2011/WD-css3-writing-modes-20110531/#text-combine),
supporting the values `none` and `horizontal` without `digits`.

`digits`

No

No

No

11

No

No

No

No

No

No

No

No

See also
--------

- [`writing-mode`](writing-mode.md),
    [`text-orientation`](text-orientation.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/text-combine-upright>

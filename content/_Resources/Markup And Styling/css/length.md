\<length\>
==========

The `<length>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
[data type](css_types.md) represents a distance value. Lengths can be used
in numerous CSS properties, such as [`width`](_Resources/Markup%20And%20Styling/css/width.md),
[`height`](_Resources/Markup%20And%20Styling/css/height.md), [`margin`](margin.md), [`padding`](padding.md),
[`border-width`](border-width.md), [`font-size`](font-size.md), and
[`text-shadow`](text-shadow.md).

**Note:** Although [`<percentage>`](percentage.md) values are usable in
some of the same properties that accept `<length>` values, they are not
themselves `<length>` values. See
[`<length-percentage>`](length-percentage.md).

Syntax
------

The `<length>` data type consists of a [`<number>`](number.md) followed by
one of the units listed below. As with all CSS dimensions, there is no
space between the number and the unit literal. Specifying the length
unit is optional if the number is `0`.

**Note:** Some properties allow negative `<length>` values, while others
do not.

The [specified value](specified_value.md) of a length (*specified length*)
is represented by its quantity and unit. The [](computed_value.md) of a length (*computed length*) is the specified
length resolved to an absolute length, and its unit is not
distinguished.

The `<length>` units can be relative or absolute. Relative lengths
represent a measurement in terms of some other distance. Depending on
the unit, this distance can be the size of a specific character, the
[line height](line-height.md), or the size of the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).
Style sheets that use relative length units can more easily scale from
one output environment to another.

**Note:** Child elements do not inherit the relative values as specified
for their parent; they inherit the computed values.

The relative length units listed here are based on font and viewport.

### Relative length units based on font

Font lengths define the `<length>` value in terms of the size of a
particular character or font attribute in the font currently in effect
in an element or its parent.

**Note:** These units, especially `em` and `rem`, are often used to
create scalable layouts, which maintain the vertical rhythm of the page
even when the user changes the font size.

[`cap`](#cap) [Experimental]

:   Represents the \"cap height\" (nominal height of capital letters) of
    the element\'s [`font`](font.md).

[`ch`](#ch)

:   Represents the width or more precisely the [advance
    measure](https://developer.mozilla.org/en-US/docs/Glossary/Advance_measure)
    of the glyph `0` (zero, the Unicode character U+0030) in the
    element\'s [`font`](font.md). In cases where it is impossible or
    impractical to determine the measure of the `0` glyph, it must be
    assumed to be `0.5em` wide by `1em` tall.

#### em

:   Represents the calculated [`font-size`](font-size.md) of the element.
    If used on the [`font-size`](font-size.md) property itself, it
    represents the *inherited* font-size of the element.

#### ex

:   Represents the [x-height](https://en.wikipedia.org/wiki/X-height) of
    the element\'s [`font`](font.md). In fonts with the `x` letter, this is
    generally the height of lowercase letters in the font; `1ex ≈ 0.5em`
    in many fonts.

[`ic`](#ic)

:   Equal to the used [advance
    measure](https://developer.mozilla.org/en-US/docs/Glossary/Advance_measure)
    of the \"水\" glyph (CJK water ideograph, U+6C34), found in the font
    used to render it.

[`lh`](#lh)

:   Equal to the computed value of the [`line-height`](line-height.md)
    property of the element on which it is used, converted to an
    absolute length.

#### rem

:   Represents the [`font-size`](font-size.md) of the root element
    (typically
    [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)).
    When used within the root element [`font-size`](font-size.md), it
    represents its initial value (a common browser default is `16px`,
    but user-defined preferences may modify this).

[`rlh`](#rlh)

:   Equal to the computed value of the [`line-height`](line-height.md)
    property on the root element (typically
    [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)),
    converted to an absolute length. When used on the
    [`font-size`](font-size.md) or [`line-height`](line-height.md) properties
    of the root element, it refers to the properties\' initial value.

### Relative length units based on viewport

The viewport-percentage length units are based on four different
viewport sizes: small, large, dynamic, and default. The allowance for
the different viewport sizes is in response to browser interfaces
expanding and retracting dynamically and hiding and showing the content
underneath.

[**Small**](#small)

:   When you want the smallest possible viewport in response to browser
    interfaces expanding dynamically, you should use the small viewport
    size. The small viewport size allows the content you design to fill
    the entire viewport when browser interfaces are expanded. Choosing
    this size might also possibly leave empty spaces when browser
    interfaces retract.

    For example, an element that is sized using viewport-percentage
    units based on the small viewport size, the element will fill the
    screen perfectly without any of its content being obscured when all
    the dynamic browser interfaces are shown. When those browser
    interfaces are hidden, however, there might be extra space visible
    around the element. Therefore, the small viewport-percentage units
    are \"safer\" to use in general, but might not produce the most
    attractive layout after a user starts interacting with the page.

    The small viewport size is represented by the `sv` prefix and
    results in the `sv*` viewport-percentage length units. The sizes of
    the small viewport-percentage units are fixed, and therefore stable,
    unless the viewport itself is resized.

[**Large**](#large)

:   When you want the largest possible viewport in response to browser
    interfaces retracting dynamically, you should use the large viewport
    size. The large viewport size allows the content you design to fill
    the entire viewport when browser interfaces are retracting. You need
    to be aware though that the content might get hidden when browser
    interfaces expand.

    For example, on mobile phones where the screen real-estate is at a
    premium, browsers often hide part or all of the title and address
    bar after a user starts scrolling the page. When an element is sized
    using a viewport-percentage unit based on the large viewport size,
    the content of the element will fill the entire visible page when
    these browser interfaces are hidden. However, when these retractable
    browser interfaces are shown, they can hide the content that is
    sized or positioned using the *large* viewport-percentage units.

    The large viewport unit is represented by the `lv` prefix and
    results in the `lv*` viewport-percentage units. The sizes of the
    large viewport-percentage units are fixed, and therefore stable,
    unless the viewport itself is resized.

[**Dynamic**](#dynamic)

:   When you want the viewport to be automatically sized in response to
    browser interfaces dynamically expanding or retracting, you can use
    the dynamic viewport size. The dynamic viewport size allows the
    content you design to fit exactly within the viewport, irrespective
    of the presence of dynamic browser interfaces.

    The dynamic viewport unit is represented by the `dv` prefix and
    results in the `dv*` viewport-percentage units. The sizes of the
    dynamic viewport-percentage units are not stable, even when the
    viewport itself is unchanged.

    
    **Note:** While the dynamic viewport size can give you more control
    and flexibility, using viewport-percentage units based on the
    dynamic viewport size can cause the content to resize while a user
    is scrolling a page. This can lead to degradation of the user
    interface and cause a performance hit.

[**Default**](#default)

:   The default viewport size is defined by the browser. The behavior of
    the resulting viewport-percentage unit could be equivalent to the
    viewport-percentage unit based on the small viewport size, the large
    viewport size, an intermediate size between the two, or the dynamic
    viewport size.

    **Note:** For example, a browser might implement the default
    viewport-percentage unit for height (`vh`) that is equivalent to the
    large viewport-percentage height unit (`lvh`). If so, this could
    obscure content on a full-page display while the browser interface
    is expanded.

Viewport-percentage lengths define `<length>` values in percentage
relative to the size of the initial [](containing_block.md), which in turn is based on either the size of
the
[viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport)
or the page area, i.e., the visible portion of the document. When the
height or width of the initial containing block is changed, the elements
that are sized based on them are scaled accordingly. There is a
viewport-percentage length unit variant corresponding to each of the
viewport sizes, as described below.

**Note:** Viewport lengths are invalid in [`@page`](@page.md) declaration
blocks.

#### vh

:   Represents a percentage of the height of the viewport\'s initial
    [containing block](containing_block.md). `1vh` is 1% of the viewport
    height. For example, if the viewport height is `300px`, then a value
    of `70vh` on a property will be `210px`.

    For small, large, and dynamic viewport sizes, the respective
    viewport-percentage units are `svh`, `lvh`, and `dvh`. `vh`
    represents the viewport-percentage length unit based on the browser
    default viewport size.

#### vw

:   Represents a percentage of the width of the viewport\'s initial
    [containing block](containing_block.md). `1vw` is 1% of the viewport
    width. For example, if the viewport width is `800px`, then a value
    of `50vw` on a property will be `400px`.

    For small, large, and dynamic viewport sizes, the respective
    viewport-percentage units are `svw`, `lvw`, and `dvw`. `vw`
    represents the viewport-percentage length unit based on the browser
    default viewport size.

#### vmax

:   Represents in percentage the largest of `vw` and `vh`.

    For small, large, and dynamic viewport sizes, the respective
    viewport-percentage units are `svmax`, `lvmax`, and `dvmax`. `vmax`
    represents the viewport-percentage length unit based on the browser
    default viewport size.

#### vmin

:   Represents in percentage the smallest of `vw` and `vh`.

    For small, large, and dynamic viewport sizes, the respective
    viewport-percentage units are `svmin`, `lvmin`, and `dvmin`. `vmin`
    represents the viewport-percentage length unit based on the browser
    default viewport size.

[`vb`](#vb)

:   Represents percentage of the size of the initial [](containing_block.md), in the direction of the root element\'s
    [block axis](css_logical_properties_and_values.md#block_vs._inline).

    For small, large, and dynamic viewport sizes, the respective
    viewport-percentage units are `svb`, `lvb`, and `dvb`, respectively.
    `vb` represents the viewport-percentage length unit based on the
    browser default viewport size.

[`vi`](#vi)

:   Represents a percentage of the size of the initial [](containing_block.md), in the direction of the root element\'s
    [inline axis](css_logical_properties_and_values.md#block_vs._inline).

    For small, large, and dynamic viewport sizes, the respective
    viewport-percentage units are `svi`, `lvi`, and `dvi`. `vi`
    represents the viewport-percentage length unit based on the browser
    default viewport size.

### Container query length units

When applying styles to a container using container queries, you can use
container query length units. These units specify a length relative to
the dimensions of a query container. Components that use units of length
relative to their container are more flexible to use in different
containers without having to recalculate concrete length values. For
more information, see [Container queries](css_container_queries.md).

[`cqw`](#cqw)

:   Represents a percentage of the width of the query container. `1cqw`
    is 1% of the query container\'s width. For example, if the query
    container\'s width is `800px`, then a value of `50cqw` on a property
    will be `400px`.

[`cqh`](#cqh)

:   Represents a percentage of the height of the query container. `1cqh`
    is 1% of the query container\'s height. For example, if the query
    container\'s height is `300px`, then a value of `10cqh` on a
    property will be `30px`.

[`cqi`](#cqi)

:   Represents a percentage of the inline size of the query container.
    `1cqi` is 1% of the query container\'s inline size. For example, if
    the query container\'s inline size is `800px`, then a value of
    `50cqi` on a property will be `400px`.

[`cqb`](#cqb)

:   Represents a percentage of the block size of the query container.
    `1cqb` is 1% of the query container\'s block size. For example, if
    the query container\'s block size is `300px`, then a value of
    `10cqb` on a property will be `30px`.

[`cqmin`](#cqmin)

:   Represents a percentage of the smaller value of either the query
    container\'s inline size or block size. `1cqmin` is 1% of the
    smaller value of either the query container\'s inline size or block
    size. For example, if the query container\'s inline size is `800px`
    and its block size is `300px`, then a value of `50cqmin` on a
    property will be `150px`.

[`cqmax`](#cqmax)

:   Represents a percentage of the larger value of either the query
    container\'s inline size or block size. `1cqmax` is 1% of the larger
    value of either the query container\'s inline size or block size.
    For example, if the query container\'s inline size is `800px` and
    its block size is `300px`, then a value of `50cqmax` on a property
    will be `400px`.

### Absolute length units

Absolute length units represent a physical measurement when the physical
properties of the output medium are known, such as for print layout.
This is done by anchoring one of the units to a physical unit and then
defining the others relative to it. The anchoring is done differently
for low-resolution devices, such as screens, versus high-resolution
devices, such as printers.

For low-dpi devices, the unit `px` represents the physical *reference
pixel*; other units are defined relative to it. Thus, `1in` is defined
as `96px`, which equals `72pt`. The consequence of this definition is
that on such devices, dimensions described in inches (`in`), centimeters
(`cm`), or millimeters (`mm`) don\'t necessarily match the size of the
physical unit with the same name.

For high-dpi devices, inches (`in`), centimeters (`cm`), and millimeters
(`mm`) are the same as their physical counterparts. Therefore, the `px`
unit is defined relative to them (1/96 of `1in`).

**Note:** Many users increase their [user
agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent)\'s
default font size to make text more legible. Absolute lengths can cause
accessibility problems because they are fixed and do not scale according
to user settings. For this reason, prefer relative lengths (such as `em`
or `rem`) when setting `font-size`.

#### px

:   One pixel. For screen displays, it traditionally represents one
    device pixel (dot). However, for *printers* and *high-resolution
    screens*, one CSS pixel implies multiple device pixels. `1px` =
    `1in / 96`.

[`cm`](#cm)

:   One centimeter. `1cm` = `96px / 2.54`.

[`mm`](#mm)

:   One millimeter. `1mm` = `1cm / 10`.

#### Q

:   One quarter of a millimeter. `1Q` = `1cm / 40`.

[`in`](#in)

:   One inch. `1in` = `2.54cm` = `96px`.

#### pc

:   One pica. `1pc` = `12pt` = `1in / 6`.

#### pt

:   One point. `1pt` = `1in / 72`.

Interpolation
-------------

When animated, values of the `<length>` data type are interpolated as
real, floating-point numbers. The interpolation happens on the
calculated value. The speed of the interpolation is determined by the
[easing function](easing-function.md) associated with the animation.

Examples
--------

### Comparing different length units

The following example provides you with an input field in which you can
enter a `<length>` value (e.g. `300px`, `50%`, `30vw`) to set the width
of a result bar that will appear below it once you\'ve pressed the
[Enter] key.

This allows you to compare and contrast the effect of different length
units.

#### HTML

[html]

```html
<div class="outer">
  <div class="input-container">
    <label for="length">Enter width:</label>
    <input type="text" id="length" />
  </div>
  <div class="inner"></div>
</div>
<div class="results"></div>
```

#### CSS

[css]

```css
html {
  font-family: sans-serif;
  font-weight: bold;
  box-sizing: border-box;
}

.outer {
  width: 100%;
  height: 50px;
  background-color: #eee;
  position: relative;
}

.inner {
  height: 50px;
  background-color: #999;
  box-shadow:
    inset 3px 3px 5px rgb(255 255 255 / 0.5),
    inset -3px -3px 5px rgb(0 0 0 / 0.5);
}

.result {
  height: 20px;
  box-shadow:
    inset 3px 3px 5px rgba(255 255 255 / 0.5),
    inset -3px -3px 5px rgb(0 0 0 / 0.5);
  background-color: orange;
  display: flex;
  align-items: center;
  margin-top: 10px;
}

.result code {
  position: absolute;
  margin-left: 20px;
}

.results {
  margin-top: 10px;
}

.input-container {
  position: absolute;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  height: 50px;
}

label {
  margin: 0 10px 0 20px;
}
```

#### JavaScript

[js]

```js
const inputDiv = document.querySelector(".inner");
const inputElem = document.querySelector("input");
const resultsDiv = document.querySelector(".results");

inputElem.addEventListener("change", () => {
  inputDiv.style.width = inputElem.value;

  const result = document.createElement("div");
  result.className = "result";
  result.style.width = inputElem.value;
  result.innerHTML = `<code>width: $</code>`;
  resultsDiv.appendChild(result);

  inputElem.value = "";
  inputElem.focus();
});
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Values and Units Module Level 4\
  [\# lengths]](https://drafts.csswg.org/css-values/#lengths)

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

`Q`

63

79

49

No

50

13.1

63

63

49

46

13.4

8.0

`length`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

`cap`

No

No

97

No

No

No

No

No

97

No

No

No

`ch`

27

12

1\[\"From Firefox 1 to Firefox 3, `ch` was the width of the *M*
character.\", \"From Firefox 1 to Firefox 3, `ch` did not work with
[`border-width`](https://developer.mozilla.org/docs/Web/CSS/border-width)
and
[`outline-width`](https://developer.mozilla.org/docs/Web/CSS/outline-width)
CSS properties.\"\]

9

15

7

4.4

27

4

15

7

1.5

`container_query_length_units`

105

105

110

No

91

16

105

105

110

72

16

20.0

`ex`

1

12

1

4

3.5

1

4.4

18

4

10.1

1

1.0

`ic`

106

106

97

No

92

15.4

106

106

97

72

15.4

20.0

`lh`

109

109

120

No

95

16.4

109

109

120

74

16.4

21.0

`rem`

4

12

3.6

9

11.6

5

2

18

4

12

4

1.0

`rlh`

No

No

120

No

No

16.4

No

No

120

No

16.4

No

`vb`

108

108

101

No

94

15.4

108

108

101

73

15.4

21.0

`vh`

20

12

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

9

20

6

4.4

25

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

14

6

1.5

`vi`

108

108

101

No

94

15.4

108

108

101

73

15.4

21.0

`viewport_percentage_units_dynamic`

108

108

101

No

94

15.4

108

108

101

73

15.4

21.0

`viewport_percentage_units_large`

108

108

101

No

94

15.4

108

108

101

73

15.4

21.0

`viewport_percentage_units_small`

108

108

101

No

94

15.4

108

108

101

73

15.4

21.0

`vmax`

26

16

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

No

15

7

1.5

26

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

14

7

1.5

`vmin`

26

1212

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

109

15

7

4.4

26

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

14

7

1.5

`vw`

20

12

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

9

20

6

4.4

25

19Starting with version 21, viewport-percentage lengths are invalid in
`@page`.

14

6

1.5

See also
--------

- [CSS values & units
    tutorial](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)
- [CSS values & units reference](css_values_and_units.md)
- [Box Model](css_box_model.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/length>

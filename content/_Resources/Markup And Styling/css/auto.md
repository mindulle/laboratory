width
=====

The `width` CSS property sets an element\'s width. By default, it sets
the width of the [](introduction_to_the_css_box_model.md#content_area), but
if [`box-sizing`](box-sizing.md) is set to `border-box`, it sets the width
of the [](introduction_to_the_css_box_model.md#border_area).

Try it
------

The specified value of `width` applies to the content area so long as
its value remains within the values defined by [`min-width`](min-width.md)
and [`max-width`](max-width.md).

- If the value for `width` is less than the value for `min-width`,
    then `min-width` overrides `width`.
- If the value for `width` is greater than the value for `max-width`,
    then `max-width` overrides `width`.

Syntax
------

[css]

```css
/* <length> values */
width: 300px;
width: 25em;

/* <percentage> value */
width: 75%;

/* Keyword values */
width: max-content;
width: min-content;
width: fit-content(20em);
width: auto;

/* Global values */
width: inherit;
width: initial;
width: revert;
width: revert-layer;
width: unset;
```

### Values

[`<length>`](length.md)

:   Defines the width as a distance value.

[`<percentage>`](percentage.md)

:   Defines the width as a percentage of the [](containing_block.md)\'s width.

[`auto`](#auto)

:   The browser will calculate and select a width for the specified
    element.

[`max-content`](#max-content)

:   The intrinsic preferred width.

[`min-content`](#min-content)

:   The intrinsic minimum width.

[`fit-content(`](#fit-content)`<length-percentage>`)

:   Uses the fit-content formula with the available space replaced by
    the specified argument, i.e.
    `min(max-content, max(min-content, <length-percentage>))`.

Accessibility concerns
----------------------

Ensure that elements set with a `width` aren\'t truncated and/or don\'t
obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements but non-replaced inline elements, table rows, and row groups
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   a percentage or `auto` or the absolute length
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
width = 
  auto                                      |
  <length-percentage [0,∞]>                 |
  min-content                               |
  max-content                               |
  fit-content( <length-percentage [0,∞]> )  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Default width

[css]

```css
p.goldie {
  background: gold;
}
```

[html]

```html
<p class="goldie">The Mozilla community produces a lot of great software.</p>
```

### Example using pixels and ems

[css]

```css
.px_length {
  width: 200px;
  background-color: red;
  color: white;
  border: 1px solid black;
}

.em_length {
  width: 20em;
  background-color: white;
  color: red;
  border: 1px solid black;
}
```

[html]

```html
<div class="px_length">Width measured in px</div>
<div class="em_length">Width measured in em</div>
```

### Example with percentage

[css]

```css
.percent {
  width: 20%;
  background-color: silver;
  border: 1px solid red;
}
```

[html]

```html
<div class="percent">Width in percentage</div>
```

### Example using \"max-content\"

[css]

```css
p.maxgreen {
  background: lightgreen;
  width: intrinsic; /* Safari/WebKit uses a non-standard name */
  width: -moz-max-content; /* Firefox/Gecko */
  width: -webkit-max-content; /* Chrome */
  width: max-content;
}
```

[html]

```html
<p class="maxgreen">The Mozilla community produces a lot of great software.</p>
```

### Example using \"min-content\"

[css]

```css
p.minblue {
  background: lightblue;
  width: -moz-min-content; /* Firefox */
  width: -webkit-min-content; /* Chrome */
  width: min-content;
}
```

[html]

```html
<p class="minblue">The Mozilla community produces a lot of great software.</p>
```

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Box Sizing Module Level 4\
  [\#
  width-height-keywords]](https://drafts.csswg.org/css-sizing-4/#width-height-keywords)

  -----------------------------------------------------------------------------------------------

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

`auto`

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

`animatable`

26

12

16

11

15

7

4.4

26

16

14

7

1.5

`fit-content`

46221--48

7979

943

No

331515--35

1172

464.44.4--48

462518--48

944

331414--35

1171

5.01.51.0--5.0

`fit-content_function`

No

No

91

No

No

No

No

No

No

No

No

No

`max-content`

4622

7979

663

No

44

112

46

46

664

43

111

5.0

`min-content`

461--48

79

663

No

3315--35

112

464.4--48

4618--48

664

3314--35

111

5.01.0--5.0

`stretch`

22

79

3

No

15

7

4.4

25

4

14

7

5.0

See also
--------

- [The box model](introduction_to_the_css_box_model.md)
- [`height`](_Resources/Markup%20And%20Styling/css/height.md)
- [`box-sizing`](box-sizing.md)
- [`min-width`](min-width.md), [`max-width`](max-width.md)
- The mapped logical properties: [`block-size`](block-size.md),
    [`inline-size`](inline-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/auto>

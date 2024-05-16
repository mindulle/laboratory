height
======

The `height` CSS property specifies the height of an element. By
default, the property defines the height of the [](introduction_to_the_css_box_model.md#content_area). If
[`box-sizing`](box-sizing.md) is set to `border-box`, however, it instead
determines the height of the [](introduction_to_the_css_box_model.md#border_area).

Try it
------

The [`min-height`](min-height.md) and [`max-height`](max-height.md) properties
override `height`.

Syntax
------

[css]

```css
/* <length> values */
height: 120px;
height: 10em;
height: 100vh;

/* <percentage> value */
height: 75%;

/* Keyword values */
height: max-content;
height: min-content;
height: fit-content(20em);
height: auto;

/* Global values */
height: inherit;
height: initial;
height: revert;
height: revert-layer;
height: unset;
```

### Values

[`<length>`](length.md)

:   Defines the height as a distance value.

[`<percentage>`](percentage.md)

:   Defines the height as a percentage of the [](containing_block.md)\'s height.

[`auto`](#auto)

:   The browser will calculate and select a height for the specified
    element.

[`max-content`](#max-content)

:   The intrinsic preferred height.

[`min-content`](#min-content)

:   The intrinsic minimum height.

[`fit-content`](#fit-content)

:   Box will use the available space, but never more than `max-content`

[`fit-content(`](#fit-content_2)`<length-percentage>`)

:   Uses the fit-content formula with the available space replaced by
    the specified argument, i.e.
    `min(max-content, max(min-content, <length-percentage>))`

[`clamp()`](clamp.md)

:   Enables selecting a middle value within a range of values between a
    defined minimum and maximum

Accessibility concerns
----------------------

Ensure that elements set with a `height` aren\'t truncated and/or don\'t
obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements but non-replaced inline elements, table columns, and column groups
  [Inherited](inheritance.md)           no
  Percentages                        The percentage is calculated with respect to the height of the generated box\'s containing block. If the height of the containing block is not specified explicitly (i.e., it depends on content height), and this element is not absolutely positioned, the value computes to `auto`. A percentage height on the root element is relative to the initial containing block.
  [Computed value](computed_value.md)   a percentage or `auto` or the absolute length
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
height = 
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

### Setting height using pixels and percentages

#### HTML

[html]

```html
<div id="taller">I'm 50 pixels tall.</div>
<div id="shorter">I'm 25 pixels tall.</div>
<div id="parent">
  <div id="child">I'm half the height of my parent.</div>
</div>
```

#### CSS

[css]

```css
div {
  width: 250px;
  margin-bottom: 5px;
  border: 2px solid blue;
}

#taller {
  height: 50px;
}

#shorter {
  height: 25px;
}

#parent {
  height: 100px;
}

#child {
  height: 50%;
  width: 75%;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------

  [CSS Box Sizing Module Level 3\
  [\#
  preferred-size-properties]](https://drafts.csswg.org/css-sizing/#preferred-size-properties)

  -----------------------------------------------------------------------------------------------------

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

`height`

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

`fit-content`

46

79

94

No

33

119

46

46

94

33

119

5.0

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

46

79

663

No

44

11

46

46

664

43

11

5.0

`min-content`

46

79

663

No

44

11

46

46

664

43

11

5.0

`stretch`

28

79

No

No

15

9

4.4

28

No

15

9

5.0

See also
--------

- [The box model](introduction_to_the_css_box_model.md)
- [`width`](_Resources/Markup%20And%20Styling/css/width.md)
- [`box-sizing`](box-sizing.md)
- [`min-height`](min-height.md), [`max-height`](max-height.md)
- The mapped logical properties: [`block-size`](block-size.md),
    [`inline-size`](inline-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/height>

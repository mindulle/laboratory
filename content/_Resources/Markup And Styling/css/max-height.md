max-height
==========

The `max-height` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the maximum height of an element. It prevents the [](used_value.md) of the [`height`](_Resources/Markup%20And%20Styling/css/height.md) property from becoming
larger than the value specified for `max-height`.

Try it
------

`max-height` overrides [`height`](_Resources/Markup%20And%20Styling/css/height.md), but
[`min-height`](min-height.md) overrides `max-height`.

Syntax
------

[css]

```css
/* <length> value */
max-height: 3.5em;

/* <percentage> value */
max-height: 75%;

/* Keyword values */
max-height: none;
max-height: max-content;
max-height: min-content;
max-height: fit-content(20em);

/* Global values */
max-height: inherit;
max-height: initial;
max-height: revert;
max-height: revert-layer;
max-height: unset;
```

### Values

[`<length>`](length.md)

:   Defines the `max-height` as an absolute value.

[`<percentage>`](percentage.md)

:   Defines the `max-height` as a percentage of the containing block\'s
    height.

[`none`](#none)

:   No limit on the size of the box.

[`max-content`](#max-content)

:   The intrinsic preferred `max-height`.

[`min-content`](#min-content)

:   The intrinsic minimum `max-height`.

[`fit-content(`](#fit-content)`<length-percentage>`)

:   Uses the `fit-content` formula with the available space replaced by
    the specified argument, i.e.
    `min(max-content, max(min-content, argument))`.

Accessibility concerns
----------------------

Ensure that elements set with a `max-height` are not truncated and/or do
not obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

Formal definition
-----------------

  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements but non-replaced inline elements, table columns, and column groups
  [Inherited](inheritance.md)           no
  Percentages                        The percentage is calculated with respect to the height of the generated box\'s containing block. If the height of the containing block is not specified explicitly (i.e., it depends on content height), and this element is not absolutely positioned, the percentage value is treated as `none`.
  [Computed value](computed_value.md)   the percentage as specified or the absolute length or `none`
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
max-height = 
  none                                      |
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

### Setting max-height using percentage and keyword values

[css]

```css
table {
  max-height: 75%;
}

form {
  max-height: none;
}
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

`max-height`

18

12

1CSS 2.1 leaves the behavior of `max-height` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Firefox supports applying `max-height` to `table` elements.

7

7CSS 2.1 leaves the behavior of `max-height` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Opera supports applying `max-height` to `table` elements.

1.3

≤37

18

4

14

1

1.0

`fit-content`

4625

7979

94

3Firefox implements the definitions given in CSS3 Basic Box. This
defines `available` and not `fit-available`. Also, the definition of
`fit-content` is simpler than in CSS3 Sizing.

No

44

1172

464.4

4625

94

4Firefox implements the definitions given in CSS3 Basic Box. This
defines `available` and not `fit-available`. Also, the definition of
`fit-content` is simpler than in CSS3 Sizing.

43

1171

5.01.5

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

119

46

46

664

43

119

5.0

`min-content`

46

79

663

No

44

119

46

46

664

43

119

5.0

`stretch`

28

79

No

No

15

No

4.4

28

No

15

No

1.5

See also
--------

- [The box model](introduction_to_the_css_box_model.md),
    [`box-sizing`](box-sizing.md)
- [`height`](_Resources/Markup%20And%20Styling/css/height.md), [`min-height`](min-height.md)
- The mapped logical properties: [`max-inline-size`](max-inline-size.md),
    [`max-block-size`](max-block-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/max-height>

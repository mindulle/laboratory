max-width
=========

The `max-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the maximum width of an element. It prevents the [](used_value.md) of the [`width`](_Resources/Markup%20And%20Styling/css/width.md) property from becoming larger
than the value specified by `max-width`.

Try it
------

`max-width` overrides [`width`](_Resources/Markup%20And%20Styling/css/width.md), but [`min-width`](min-width.md)
overrides `max-width`.

Syntax
------

[css]

```css
/* <length> value */
max-width: 3.5em;

/* <percentage> value */
max-width: 75%;

/* Keyword values */
max-width: none;
max-width: max-content;
max-width: min-content;
max-width: fit-content(20em);

/* Global values */
max-width: inherit;
max-width: initial;
max-width: revert;
max-width: revert-layer;
max-width: unset;
```

### Values

[`<length>`](length.md)

:   Defines the `max-width` as an absolute value.

[`<percentage>`](percentage.md)

:   Defines the `max-width` as a percentage of the containing block\'s
    width.

[`none`](#none)

:   No limit on the size of the box.

[`max-content`](#max-content)

:   The intrinsic preferred `max-width`.

[`min-content`](#min-content)

:   The intrinsic minimum `max-width`.

[`fit-content(`](#fit-content)`<length-percentage>`)

:   Uses the `fit-content` formula with the available space replaced by
    the specified argument, i.e.
    `min(max-content, max(min-content, argument))`.

Accessibility concerns
----------------------

Ensure that elements set with a `max-width` are not truncated and/or do
not obscure other content when the page is zoomed to increase text size.

- [MDN Understanding WCAG, Guideline 1.4
    explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 \| W3C Understanding WCAG
    2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements but non-replaced inline elements, table rows, and row groups
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   the percentage as specified or the absolute length or `none`
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
max-width = 
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

### Setting max width in pixels

In this example, the \"child\" will be either 150 pixels wide or the
width of the \"parent,\" whichever is smaller.

#### HTML

[html]

```html
<div id="parent">
  <div id="child">
    Fusce pulvinar vestibulum eros, sed luctus ex lobortis quis.
  </div>
</div>
```

#### CSS

[css]

```css
#parent {
  background: lightblue;
  width: 300px;
}

#child {
  background: gold;
  width: 100%;
  max-width: 150px;
}
```

#### Result

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

`max-width`

1

12

1CSS 2.1 leaves the behavior of `max-width` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Firefox supports applying `max-width` to `table` elements.

7

4CSS 2.1 leaves the behavior of `max-width` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Opera supports applying `max-width` to `table` elements.

1

4.4

18

4CSS 2.1 leaves the behavior of `max-width` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Firefox supports applying `max-width` to `table` elements.

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

46≤37

46

94

4Firefox implements the definitions given in CSS3 Basic Box. This
defines `available` and not `fit-available`. Also, the definition of
`fit-content` is simpler than in CSS3 Sizing.

43

1171

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

4622

7979

663

No

44

1172

46≤37

46

664

43

1171

5.0

`min-content`

4625

7979

663

No

44

1172

46

46

664

43

1171

5.0

`stretch`

22

79

No

No

15

No

4.4

25

No

14

No

1.5

See also
--------

- [The box model](introduction_to_the_css_box_model.md),
    [`box-sizing`](box-sizing.md)
- [`width`](_Resources/Markup%20And%20Styling/css/width.md), [`min-width`](min-width.md)
- The mapped logical properties: [`max-inline-size`](max-inline-size.md),
    [`max-block-size`](max-block-size.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/max-width>

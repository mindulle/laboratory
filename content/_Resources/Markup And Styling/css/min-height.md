min-height
==========

The `min-height` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the minimum height of an element. It prevents the [](used_value.md) of the [`height`](_Resources/Markup%20And%20Styling/css/height.md) property from becoming
smaller than the value specified for `min-height`.

Try it
------

The element\'s height is set to the value of `min-height` whenever
`min-height` is larger than [`max-height`](max-height.md) or
[`height`](_Resources/Markup%20And%20Styling/css/height.md).

Syntax
------

[css]

```css
/* <length> value */
min-height: 3.5em;

/* <percentage> value */
min-height: 10%;

/* Keyword values */
min-height: max-content;
min-height: min-content;
min-height: fit-content(20em);

/* Global values */
min-height: inherit;
min-height: initial;
min-height: revert;
min-height: revert-layer;
min-height: unset;
```

### Values

[`<length>`](length.md)

:   Defines the `min-height` as an absolute value.

[`<percentage>`](percentage.md)

:   Defines the `min-height` as a percentage of the containing block\'s
    height.

[`auto`](#auto)

:   The browser will calculate and select a `min-height` for the
    specified element.

[`max-content`](#max-content)

:   The intrinsic preferred `min-height`.

[`min-content`](#min-content)

:   The intrinsic minimum `min-height`.

[`fit-content(`](#fit-content)`<length-percentage>`)

:   Uses the `fit-content` formula with the available space replaced by
    the specified argument, i.e.
    `min(max-content, max(min-content, argument))`.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements but non-replaced inline elements, table columns, and column groups
  [Inherited](inheritance.md)           no
  Percentages                        The percentage is calculated with respect to the height of the generated box\'s containing block. If the height of the containing block is not specified explicitly (i.e., it depends on content height), and this element is not absolutely positioned, the percentage value is treated as `0`.
  [Computed value](computed_value.md)   the percentage as specified or the absolute length
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
min-height = 
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

### Setting min-height

[css]

```css
table {
  min-height: 75%;
}

form {
  min-height: 0;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------

Specification
  ---------------------------------------------------------------------------------------------

  [CSS Box Sizing Module Level 3\
  [\#
  width-height-keywords]](https://drafts.csswg.org/css-sizing/#width-height-keywords)

  ---------------------------------------------------------------------------------------------

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

`min-height`

1

12

3CSS 2.1 leaves the behavior of `min-height` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Firefox supports applying `min-height` to `table` elements.

7In Internet Explorer 10 and 11, a `min-height` declaration on a
column-direction flex container doesn\'t apply to the container\'s flex
items. See [Flexbug
\#3](https://github.com/philipwalton/flexbugs#3-min-height-on-a-column-flex-container-wont-apply-to-its-flex-items)
for more info.

4CSS 2.1 leaves the behavior of `min-height` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Opera supports applying `min-height` to `table` elements.

1.3

4.4

18

4CSS 2.1 leaves the behavior of `min-height` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Firefox supports applying `min-height` to `table` elements.

14

1

1.0

`auto`

21

79

16--22Firefox 18 and later used `auto` as the initial value for
`min-height`.

No

12.1

7

37

25

16--22Firefox 18 and later used `auto` as the initial value for
`min-height`.

14

7

1.5

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

9

4.4

28

No

15

9

1.5

See also
--------

- [The box model](introduction_to_the_css_box_model.md),
    [`box-sizing`](box-sizing.md)
- [`height`](_Resources/Markup%20And%20Styling/css/height.md), [`max-height`](max-height.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/min-height>

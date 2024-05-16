min-width
=========

The `min-width` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property sets the minimum width of an element. It prevents the [](used_value.md) of the [`width`](_Resources/Markup%20And%20Styling/css/width.md) property from becoming
smaller than the value specified for `min-width`.

Try it
------

The element\'s width is set to the value of `min-width` whenever
`min-width` is larger than [`max-width`](max-width.md) or [`width`](_Resources/Markup%20And%20Styling/css/width.md).

Syntax
------

[css]

```css
/* <length> value */
min-width: 3.5em;

/* <percentage> value */
min-width: 10%;

/* Keyword values */
min-width: max-content;
min-width: min-content;
min-width: fit-content(20em);

/* Global values */
min-width: inherit;
min-width: initial;
min-width: revert;
min-width: revert-layer;
min-width: unset;
```

### Values

[`<length>`](length.md)

:   Defines the `min-width` as an absolute value.

[`<percentage>`](percentage.md)

:   Defines the `min-width` as a percentage of the containing block\'s
    width.

[`auto`](#auto)

:   The browser will calculate and select a `min-width` for the
    specified element.

[`max-content`](#max-content)

:   The intrinsic preferred `min-width`.

[`min-content`](#min-content)

:   The intrinsic minimum `min-width`.

[`fit-content(`](#fit-content)`<length-percentage>`)

:   Uses the `fit-content` formula with the available space replaced by
    the specified argument, i.e.
    `min(max-content, max(min-content, argument))`.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         all elements but non-replaced inline elements, table rows, and row groups
  [Inherited](inheritance.md)           no
  Percentages                        refer to the width of the containing block
  [Computed value](computed_value.md)   the percentage as specified or the absolute length
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
min-width = 
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

### Setting minimum element width

[css]

```css
table {
  min-width: 75%;
}

form {
  min-width: 0;
}
```

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Box Sizing Module Level 3\
  [\#
  min-size-properties]](https://drafts.csswg.org/css-sizing/#min-size-properties)

  -----------------------------------------------------------------------------------------

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

`min-width`

1

12

1CSS 2.1 leaves the behavior of `min-width` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Firefox supports applying `min-width` to `table` elements.

7

4CSS 2.1 leaves the behavior of `min-width` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Opera supports applying `min-width` to `table` elements.

1

4.4

18

4CSS 2.1 leaves the behavior of `min-width` with
[`table`](https://developer.mozilla.org/docs/Web/HTML/Element/table)
undefined. Firefox supports applying `min-width` to `table` elements.

10.1

1

1.0

`auto`

21Chrome uses `auto` as the initial value for `min-width`.

12Edge uses `auto` as the initial value for `min-width`.

34

16--22Firefox 18 and later (until the value was removed), used `auto` as
the initial value for `min-width`.

No

12.1Opera uses `auto` as the initial value for `min-width`.

7

37Chrome uses `auto` as the initial value for `min-width`.

25Chrome uses `auto` as the initial value for `min-width`.

34

16--22Firefox 18 and later (until the value was removed), used `auto` as
the initial value for `min-width`.

14Opera uses `auto` as the initial value for `min-width`.

7

1.5Samsung Internet uses `auto` as the initial value for `min-width`.

`fit-content`

4625

7979

94

3Firefox implements the definitions given in CSS3 Basic Box. This
defines `available` and not `fit-available`. Also, the definition of
`fit-content` is simpler than in CSS3 Sizing.

No

3315

117

46≤37

46

94

4Firefox implements the definitions given in CSS3 Basic Box. This
defines `available` and not `fit-available`. Also, the definition of
`fit-content` is simpler than in CSS3 Sizing.

33

117

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

4625

7979

663

No

3315

112

46≤37

46

664

33

111

5.0

`min-content`

462525--48

7979

663

No

33≤15≤15--35

112

464.44.4--48

462525--48

664

33≤14≤14--35

111

5.01.51.5--5.0

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

- [`width`](_Resources/Markup%20And%20Styling/css/width.md), [`max-width`](max-width.md)
- The [box model](introduction_to_the_css_box_model.md),
    [`box-sizing`](box-sizing.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/min-width>

min-block-size
==============

The `min-block-size`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the minimum horizontal or vertical size of an element\'s block,
depending on its writing mode. It corresponds to either the
[`min-width`](min-width.md) or the [`min-height`](min-height.md) property,
depending on the value of [`writing-mode`](writing-mode.md).

If the writing mode is vertically oriented, the value of
`min-block-size` relates to the minimum width of the element; otherwise,
it relates to the minimum height of the element. A related property is
[`min-inline-size`](min-inline-size.md), which defines the other dimension
of the element.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
min-block-size: 100px;
min-block-size: 5em;

/* <percentage> values */
min-block-size: 10%;

/* Keyword values */
min-block-size: max-content;
min-block-size: min-content;
min-block-size: fit-content(20em);

/* Global values */
min-block-size: inherit;
min-block-size: initial;
min-block-size: revert;
min-block-size: revert-layer;
min-block-size: unset;
```

### Values

The `min-block-size` property takes the same values as the
[`min-width`](min-width.md) and [`min-height`](min-height.md) properties.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         same as [`width`](_Resources/Markup%20And%20Styling/css/width.md) and [`height`](_Resources/Markup%20And%20Styling/css/height.md)
  [Inherited](inheritance.md)           no
  Percentages                        block-size of containing block
  [Computed value](computed_value.md)   same as [`min-width`](min-width.md) and [`min-height`](min-height.md)
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
min-block-size = 
  <'min-width'>  
```

Examples
--------

### Setting minimum block size for vertical text

#### HTML

[html]

```html
<p class="exampleText">Example text</p>
```

#### CSS

[css]

```css
.exampleText {
  writing-mode: vertical-rl;
  background-color: yellow;
  min-block-size: 200px;
}
```

#### Result

Specifications
--------------

  ------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-min-block-size]](https://drafts.csswg.org/css-logical/#propdef-min-block-size)

  ------------------------------------------------------------------------------------------------

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

`min-block-size`

57

79

41

No

44

12.1

57

57

41

43

12.2

7.0

`fit-content`

57

79

94

No

44

12.1

57

57

94

43

12.2

7.0

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

57

79

6641

No

44

12.1

57

57

6641

43

12.2

7.0

`min-content`

57

79

6641

No

44

12.1

57

57

6641

43

12.2

7.0

See also
--------

- The mapped physical properties: [`min-width`](min-width.md) and
    [`min-height`](min-height.md)
- [`writing-mode`](writing-mode.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/min-block-size>

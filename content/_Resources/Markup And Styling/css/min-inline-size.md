min-inline-size
===============

The `min-inline-size`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the horizontal or vertical minimal size of an element\'s block,
depending on its writing mode. It corresponds to either the
[`min-width`](min-width.md) or the [`min-height`](min-height.md) property,
depending on the value of [`writing-mode`](writing-mode.md).

Try it
------

Syntax
------

[css]

```css
/* <length> values */
min-inline-size: 100px;
min-inline-size: 5em;

/* <percentage> values */
min-inline-size: 10%;

/* Keyword values */
min-inline-size: max-content;
min-inline-size: min-content;
min-inline-size: fit-content(20em);

/* Global values */
min-inline-size: inherit;
min-inline-size: initial;
min-inline-size: revert;
min-inline-size: revert-layer;
min-inline-size: unset;
```

If the writing mode is vertically oriented, the value of
`min-inline-size` relates to the minimum height of the element;
otherwise, it relates to the minimum width of the element. A related
property is [`min-block-size`](min-block-size.md), which defines the other
dimension of the element.

### Values

The `min-inline-size` property takes the same values as the
[`min-width`](min-width.md) and [`min-height`](min-height.md) properties.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         same as [`width`](_Resources/Markup%20And%20Styling/css/width.md) and [`height`](_Resources/Markup%20And%20Styling/css/height.md)
  [Inherited](inheritance.md)           no
  Percentages                        inline-size of containing block
  [Computed value](computed_value.md)   same as [`min-width`](min-width.md) and [`min-height`](min-height.md)
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
min-inline-size = 
  <'min-width'>  
```

Examples
--------

### Setting minimum inline size for vertical text

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
  block-size: 5%;
  min-inline-size: 200px;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  propdef-min-inline-size]](https://drafts.csswg.org/css-logical/#propdef-min-inline-size)

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

`min-inline-size`

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

9441

No

44

12.1

57

57

9441

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
https://developer.mozilla.org/en-US/docs/Web/CSS/min-inline-size>

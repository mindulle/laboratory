max-inline-size
===============

The `max-inline-size`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the horizontal or vertical maximum size of an element\'s block,
depending on its writing mode. It corresponds to either the
[`max-width`](max-width.md) or the [`max-height`](max-height.md) property,
depending on the value of [`writing-mode`](writing-mode.md).

If the writing mode is vertically oriented, the value of
`max-inline-size` relates to the maximal height of the element;
otherwise, it relates to the maximal width of the element. A related
property is [`max-block-size`](max-block-size.md), which defines the other
dimension of the element.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
max-inline-size: 300px;
max-inline-size: 25em;

/* <percentage> values */
max-inline-size: 75%;

/* Keyword values */
max-inline-size: none;
max-inline-size: max-content;
max-inline-size: min-content;
max-inline-size: fit-content(20em);

/* Global values */
max-inline-size: inherit;
max-inline-size: initial;
max-inline-size: revert;
max-inline-size: revert-layer;
max-inline-size: unset;
```

### Values

The `max-inline-size` property takes the same values as the
[`max-width`](max-width.md) and [`max-height`](max-height.md) properties.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         same as [`width`](_Resources/Markup%20And%20Styling/css/width.md) and [`height`](_Resources/Markup%20And%20Styling/css/height.md)
  [Inherited](inheritance.md)           no
  Percentages                        inline-size of containing block
  [Computed value](computed_value.md)   same as [`max-width`](max-width.md) and [`max-height`](max-height.md)
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
max-inline-size = 
  <'max-width'>  
```

Examples
--------

### Setting maximum inline size in pixels

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
  block-size: 100%;
  max-inline-size: 200px;
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
  propdef-max-inline-size]](https://drafts.csswg.org/css-logical/#propdef-max-inline-size)

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

`max-inline-size`

57

79

41

No

44

12.110.1

57

57

41

43

12.210.3

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

- The mapped physical properties: [`max-width`](max-width.md) and
    [`max-height`](max-height.md)
- [`writing-mode`](writing-mode.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/max-inline-size>

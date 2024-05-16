inline-size
===========

The `inline-size`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
the horizontal or vertical size of an element\'s block, depending on its
writing mode. It corresponds to either the [`width`](_Resources/Markup%20And%20Styling/css/width.md) or the
[`height`](_Resources/Markup%20And%20Styling/css/height.md) property, depending on the value of
[`writing-mode`](writing-mode.md).

If the writing mode is vertically oriented, the value of `inline-size`
relates to the height of the element; otherwise, it relates to the width
of the element. A related property is [`block-size`](block-size.md), which
defines the other dimension of the element.

Try it
------

Syntax
------

[css]

```css
/* <length> values */
inline-size: 300px;
inline-size: 25em;

/* <percentage> values */
inline-size: 75%;

/* Keyword values */
inline-size: max-content;
inline-size: min-content;
inline-size: fit-content(20em);
inline-size: auto;

/* Global values */
inline-size: inherit;
inline-size: initial;
inline-size: revert;
inline-size: revert-layer;
inline-size: unset;
```

### Values

The `inline-size` property takes the same values as the [`width`](_Resources/Markup%20And%20Styling/css/width.md)
and [`height`](_Resources/Markup%20And%20Styling/css/height.md) properties.

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `auto`
  Applies to                         same as [`width`](_Resources/Markup%20And%20Styling/css/width.md) and [`height`](_Resources/Markup%20And%20Styling/css/height.md)
  [Inherited](inheritance.md)           no
  Percentages                        inline-size of containing block
  [Computed value](computed_value.md)   same as [`width`](_Resources/Markup%20And%20Styling/css/width.md) and [`height`](_Resources/Markup%20And%20Styling/css/height.md)
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
inline-size = 
  <'width'>  
```

Examples
--------

### Setting inline size in pixels

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
  inline-size: 110px;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------

  [CSS Logical Properties and Values Level 1\
  [\#
  dimension-properties]](https://drafts.csswg.org/css-logical/#dimension-properties)

  --------------------------------------------------------------------------------------------

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

`inline-size`

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

5.0

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

5.0

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

5.0

See also
--------

- The mapped physical properties: [`width`](_Resources/Markup%20And%20Styling/css/width.md) and
    [`height`](_Resources/Markup%20And%20Styling/css/height.md)
- [`writing-mode`](writing-mode.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/inline-size>

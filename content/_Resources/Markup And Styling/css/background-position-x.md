background-position-x
=====================

The `background-position-x`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the initial horizontal position for each background image. The position
is relative to the position layer set by
[`background-origin`](background-origin.md).

Try it
------

The value of this property is overridden by any declaration of the
[`background`](background.md) or
[`background-position`](background-position.md) shorthand properties
applied to the element after it.

Syntax
------

[css]

```css
/* Keyword values */
background-position-x: left;
background-position-x: center;
background-position-x: right;

/* <percentage> values */
background-position-x: 25%;

/* <length> values */
background-position-x: 0px;
background-position-x: 1cm;
background-position-x: 8em;

/* Side-relative values */
background-position-x: right 3px;
background-position-x: left 25%;

/* Multiple values */
background-position-x: 0px, center;

/* Global values */
background-position-x: inherit;
background-position-x: initial;
background-position-x: revert;
background-position-x: revert-layer;
background-position-x: unset;
```

The `background-position-x` property is specified as one or more values,
separated by commas.

### Values

[`left`](#left)

:   Aligns the left edge of the background image with the left edge of
    the background position layer.

[`center`](#center)

:   Aligns the center of the background image with the center of the
    background position layer.

[`right`](#right)

:   Aligns the right edge of the background image with the right edge of
    the background position layer.

[`<length>`](length.md)

:   The offset of the given background image\'s left vertical edge from
    the background position layer\'s left vertical edge. (Some browsers
    allow assigning the right edge for offset).

[`<percentage>`](percentage.md)

:   The offset of the given background image\'s horizontal position
    relative to the container. A value of 0% means that the left edge of
    the background image is aligned with the left edge of the container,
    and a value of 100% means that the *right* edge of the background
    image is aligned with the *right* edge of the container, thus a
    value of 50% horizontally centers the background image.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0%`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to width of background positioning area minus width of background image
  [Computed value](computed_value.md)   A list, each item consisting of: an offset given as a combination of an absolute length and a percentage, plus an origin keyword
  Animation type                     a repeatable list
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-position-x = 
  [ center | [ [ left | right | x-start | x-end ]? <length-percentage>? ]! ]#  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Basic example

The following example shows a simple background image implementation,
with background-position-x and background-position-y used to define the
image\'s horizontal and vertical positions separately.

#### HTML

[html]

```html
<div></div>
```

#### CSS

[css]

```css
div {
  width: 300px;
  height: 300px;
  background-color: skyblue;
  background-image: url(https://mdn.dev/archives/media/attachments/2020/07/29/17350/3b4892b7e820122ac6dd7678891d4507/firefox.png);
  background-repeat: no-repeat;
  background-position-x: center;
  background-position-y: bottom 10px;
}
```

#### Result

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 4\
  [\#
  background-position-longhands]](https://drafts.csswg.org/css-backgrounds-4/#background-position-longhands)

  --------------------------------------------------------------------------------------------------------------------

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

`background-position-x`

1

12

49

6

15

1

≤37

18

49

14

1

1.0

`two_value_syntax`

No

12--79

49

9

No

15.4

No

No

49

No

15.4

No

See also
--------

- [`background-position`](background-position.md)
- [`background-position-y`](background-position-y.md)
- [`background-position-inline`]
- [`background-position-block`]
- [](using_multiple_backgrounds.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-x>

background-position-y
=====================

The `background-position-y`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
the initial vertical position for each background image. The position is
relative to the position layer set by
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
background-position-y: top;
background-position-y: center;
background-position-y: bottom;

/* <percentage> values */
background-position-y: 25%;

/* <length> values */
background-position-y: 0px;
background-position-y: 1cm;
background-position-y: 8em;

/* Side-relative values */
background-position-y: bottom 3px;
background-position-y: bottom 10%;

/* Multiple values */
background-position-y: 0px, center;

/* Global values */
background-position-y: inherit;
background-position-y: initial;
background-position-y: revert;
background-position-y: revert-layer;
background-position-y: unset;
```

The `background-position-y` property is specified as one or more values,
separated by commas.

### Values

[`top`](#top)

:   Aligns the top edge of the background image with the top edge of the
    background position layer.

[`center`](#center)

:   Aligns the vertical center of the background image with the vertical
    center of the background position layer.

[`bottom`](#bottom)

:   Aligns the bottom edge of the background image with the bottom edge
    of the background position layer.

[`<length>`](length.md)

:   The offset of the given background image\'s horizontal edge from the
    corresponding background position layer\'s top horizontal edge.
    (Some browsers allow assigning the bottom edge for offset).

[`<percentage>`](percentage.md)

:   The offset of the given background image\'s vertical position
    relative to the container. A value of 0% means that the top edge of
    the background image is aligned with the top edge of the container,
    and a value of 100% means that the *bottom* edge of the background
    image is aligned with the *bottom* edge of the container, thus a
    value of 50% vertically centers the background image.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0%`
  Applies to                         all elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to height of background positioning area minus height of background image
  [Computed value](computed_value.md)   A list, each item consisting of: an offset given as a combination of an absolute length and a percentage, plus an origin keyword
  Animation type                     a repeatable list
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
background-position-y = 
  [ center | [ [ top | bottom | y-start | y-end ]? <length-percentage>? ]! ]#  

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

`2_value_syntax`

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

`background-position-y`

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

See also
--------

- [`background-position`](background-position.md)
- [`background-position-x`](background-position-x.md)
- [`background-position-inline`]
- [`background-position-block`]
- [](using_multiple_backgrounds.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/background-position-y>

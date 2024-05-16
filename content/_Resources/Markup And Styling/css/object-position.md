object-position
===============

The `object-position`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property
specifies the alignment of the selected [](replaced_element.md)\'s contents within the element\'s box. Areas
of the box which aren\'t covered by the replaced element\'s object will
show the element\'s background.

You can adjust how the replaced element\'s object\'s intrinsic size
(that is, its natural size) is adjusted to fit within the element\'s box
using the [`object-fit`](object-fit.md) property.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
object-position: top;
object-position: bottom;
object-position: left;
object-position: right;
object-position: center;

/* <percentage> values */
object-position: 25% 75%;

/* <length> values */
object-position: 0 0;
object-position: 1cm 2cm;
object-position: 10ch 8em;

/* Edge offsets values */
object-position: bottom 10px right 20px;
object-position: right 3em bottom 10px;
object-position: top 0 right 10px;

/* Global values */
object-position: inherit;
object-position: initial;
object-position: revert;
object-position: revert-layer;
object-position: unset;
```

### Values

[`<position>`](position_value.md)

:   From one to four values that define the 2D position of the element.
    Relative or absolute offsets can be used.

**Note:** The position can be set so that the replaced element is drawn
outside its box.

Formal definition
-----------------

  ---------------------------------- ---------------------------------------------
  [Initial value](initial_value.md)     `50% 50%`
  Applies to                         replaced elements
  [Inherited](inheritance.md)           yes
  Percentages                        refer to width and height of element itself
  [Computed value](computed_value.md)   as specified
  Animation type                     a repeatable list
  ---------------------------------- ---------------------------------------------

Formal syntax
-------------

```
object-position = 
  <position>  

<position> = 
  [ left | center | right ] || [ top | center | bottom ]  |
  [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]?  |
  [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ]  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Positioning image content

#### HTML

Here we see HTML that includes two
[`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)
elements, each displaying the MDN logo.

[html]

```html
<img id="object-position-1" src="mdn.svg" alt="MDN Logo" />
<img id="object-position-2" src="mdn.svg" alt="MDN Logo" />
```

#### CSS

The CSS includes default styling for the `<img>` element itself, as well
as separate styles for each of the two images.

[css]

```css
img {
  width: 300px;
  height: 250px;
  border: 1px solid black;
  background-color: silver;
  margin-right: 1em;
  object-fit: none;
}

#object-position-1 {
  object-position: 10px;
}

#object-position-2 {
  object-position: 100% 10%;
}
```

The first image is positioned with its left edge inset 10 pixels from
the left edge of the element\'s box. The second image is positioned with
its right edge flush against the right edge of the element\'s box and is
located 10% of the way down the height of the element\'s box.

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------

  [CSS Images Module Level 3\
  [\#
  the-object-position]](https://drafts.csswg.org/css-images/#the-object-position)

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

`object-position`

32

79

16--79Only supported for `<img>` elements.

36

No

1911.6--15

10

4.4.3

32

36

1912--14

10

2.0

See also
--------

- Other image-related CSS properties: [`object-fit`](object-fit.md),
    [`image-orientation`](image-orientation.md),
    [`image-rendering`](image-rendering.md),
    [`image-resolution`](image-resolution.md).

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/object-position>

shape-outside
=============

The `shape-outside`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines
a shape---which may be non-rectangular---around which adjacent inline
content should wrap. By default, inline content wraps around its margin
box; `shape-outside` provides a way to customize this wrapping, making
it possible to wrap text around complex objects rather than simple
boxes.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
shape-outside: none;
shape-outside: margin-box;
shape-outside: content-box;
shape-outside: border-box;
shape-outside: padding-box;

/* Function values */
shape-outside: circle();
shape-outside: ellipse();
shape-outside: inset(10px 10px 10px 10px);
shape-outside: polygon(10px 10px, 20px 20px, 30px 30px);
shape-outside: path("M100,0 A100,100 0 1,1 100,200 A100,100 0 1,1 100,0");

/* <url> value */
shape-outside: url(image.png);

/* <gradient> value */
shape-outside: linear-gradient(45deg, #fff 150px, red 150px);

/* Global values */
shape-outside: inherit;
shape-outside: initial;
shape-outside: revert;
shape-outside: revert-layer;
shape-outside: unset;
```

The `shape-outside` property is specified using the values from the list
below, which define the *float area* for *float elements*. The float
area determines the shape around which inline content (float elements)
wrap.

### Values

[`none`](#none)

:   The float area is unaffected. Inline content wraps around the
    element\'s margin box, like usual.

[`<shape-box>`](#shape-box)

:   The float area is computed according to the shape of a float
    element\'s edges (as defined by the [](introduction_to_the_css_box_model.md)). This can
    be `margin-box`, `border-box`, `padding-box`, or `content-box`. The
    shape includes any curvature created by the
    [`border-radius`](border-radius.md) property (behavior which is similar
    to [`background-clip`](background-clip.md)).

    [`margin-box`](#margin-box)

    :   Defines the shape enclosed by the outside margin edge. The
        corner radii of this shape are determined by the corresponding
        [`border-radius`](border-radius) and [`margin`](margin) values.
        If the `border-radius / margin` ratio is `1` or more, then the
        margin box corner radius is `border-radius + margin`. If the
        ratio is less than `1`, then the margin box corner radius is
        `border-radius + (margin * (1 + (ratio - 1) ^ 3))`.

    [`border-box`](#border-box)

    :   Defines the shape enclosed by the outside border edge. The shape
        follows the normal border radius shaping rules for the outside
        of the border.

    [`padding-box`](#padding-box)

    :   Defines the shape enclosed by the outside padding edge. The
        shape follows the normal border radius shaping rules for the
        inside of the border.

    [`content-box`](#content-box)

    :   Defines the shape enclosed by the outside content edge. Each
        corner radius of this box is the larger of `0` or
        `border-radius - border-width - padding`.

[`<basic-shape>`](basic-shape.md)

:   The float area is computed based on the shape created by of one of
    [`inset()`](_Resources/Markup%20And%20Styling/css/basic-shape/inset.md), [`circle()`](circle.md),
    [`ellipse()`](ellipse.md),
    [`polygon()`](polygon.md) or, as added in the level 2
    specification, `path()`. If a `<shape-box>` is also supplied, it
    defines the reference box for the `<basic-shape>` function.
    Otherwise, the reference box defaults to `margin-box`.

[`<image>`](_Resources/Markup%20And%20Styling/css/image.md)

:   The float area is extracted and computed based on the alpha channel
    of the specified [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) as defined by
    [`shape-image-threshold`](shape-image-threshold.md).

**Note:** If the image is invalid, the effect is as if the keyword
`none` had been specified. Additionally, the image must be served with
[CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) headers
allowing its use.

Formal definition
-----------------

  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         floats
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as defined for [`<basic-shape>`](basic-shape.md) (with [`shape-box`](shape-outside.md) following, if supplied), the [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) with its URI made absolute, otherwise as specified.
  Animation type                     yes, as specified for [`<basic-shape>`](basic-shape.md), otherwise no
  ---------------------------------- --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
shape-outside = 
  none                              |
  [ <basic-shape> || <shape-box> ]  |
  <image>                           

<shape-box> = 
  <box>       |
  margin-box  

<image> = 
  <url>       |
  <gradient>  

<box> = 
  border-box   |
  padding-box  |
  content-box  

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  
```

Examples
--------

### Funneling text

#### HTML

[html]

```html
<div class="main">
  <div class="left"></div>
  <div class="right"></div>
  <p>
    Sometimes a web page's text content appears to be funneling your attention
    towards a spot on the page to drive you to follow a particular link.
    Sometimes you don't notice.
  </p>
</div>
```

#### CSS

[css]

```css
.main {
  width: 530px;
}

.left,
.right {
  background-color: lightgray;
  height: 12ex;
  width: 40%;
}

.left {
  clip-path: polygon(0 0, 100% 100%, 0 100%);
  float: left;
  shape-outside: polygon(0 0, 100% 100%, 0 100%);
}

.right {
  clip-path: polygon(100% 0, 100% 100%, 0 100%);
  float: right;
  shape-outside: polygon(100% 0, 100% 100%, 0 100%);
}

p {
  text-align: center;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  shape-outside-property]](https://drafts.csswg.org/css-shapes/#shape-outside-property)

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

`shape-outside`

37

79

62

No

24

10.1

37

37

62

24

10.3

3.0

`circle`

37

79

62

No

24

10.1

37

37

62

24

10.3

3.0

`gradient`

37

79

62

No

24

10.1

37

37

62

24

10.3

3.0

`image`

37

79

62

No

24

10.1

37

37

62

24

10.3

3.0

`inset`

37

79

62

No

24

10.1

37

37

62

24

10.3

3.0

`path`

No

No

No

No

No

No

No

No

No

No

No

No

`polygon`

37

79

62

No

24

10.1

37

37

62

24

10.3

3.0

See also
--------

- [CSS shapes](css_shapes.md)
- [Overview of shapes](overview_of_shapes.md)
- [`<basic-shape>`](basic-shape.md)
- [`shape-margin`](shape-margin.md)
- [`shape-image-threshold`](shape-image-threshold.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/shape-outside>

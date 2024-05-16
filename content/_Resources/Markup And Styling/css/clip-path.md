clip-path
=========

The `clip-path` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
property creates a clipping region that sets what part of an element
should be shown. Parts that are inside the region are shown, while those
outside are hidden.

Try it
------

Syntax
------

[css]

```css
/* Keyword values */
clip-path: none;

/* <clip-source> values */
clip-path: url(resources.svg#c1);

/* <geometry-box> values */
clip-path: margin-box;
clip-path: border-box;
clip-path: padding-box;
clip-path: content-box;
clip-path: fill-box;
clip-path: stroke-box;
clip-path: view-box;

/* <basic-shape> values */
clip-path: inset(100px 50px);
clip-path: circle(50px at 0 100px);
clip-path: ellipse(50px 60px at 0 10% 20%);
clip-path: polygon(50% 0%, 100% 50%, 50% 100%, 0% 50%);
clip-path: path(
  "M0.5,1 C0.5,1,0,0.7,0,0.3 A0.25,0.25,1,1,1,0.5,0.3 A0.25,0.25,1,1,1,1,0.3 C1,0.7,0.5,1,0.5,1 Z"
);

/* Box and shape values combined */
clip-path: padding-box circle(50px at 0 100px);

/* Global values */
clip-path: inherit;
clip-path: initial;
clip-path: revert;
clip-path: revert-layer;
clip-path: unset;
```

The `clip-path` property is specified as one or a combination of the
values listed below.

### Values

[`<clip-source>`](#clip-source)

:   A [`url()`](url.md) referencing an
    [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG)
    [`<clipPath>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/clipPath)
    element.

[`<basic-shape>`](basic-shape.md)

:   A shape whose size and position is defined by the `<geometry-box>`
    value. If no geometry box is specified, the `border-box` will be
    used as the reference box. One of:

    [`inset()`](basic-shape/inset)

    :   Defines an inset rectangle.

    [`circle()`](basic-shape/circle)

    :   Defines a circle using a radius and a position.

    [`ellipse()`](basic-shape/ellipse)

    :   Defines an ellipse using two radii and a position.

    [`polygon()`](basic-shape/polygon)

    :   Defines a polygon using an SVG filling rule and a set of
        vertices.

    [`path()`](path)

    :   Defines a shape using an optional SVG filling rule and an SVG
        path definition.

[`<geometry-box>`](#geometry-box)

:   If specified in combination with a `<basic-shape>`, this value
    defines the reference box for the basic shape. If specified by
    itself, it causes the edges of the specified box, including any
    corner shaping (such as a [`border-radius`](border-radius.md)), to be
    the clipping path. The geometry box can be one of the following
    values:

    [`margin-box`](#margin-box)

    :   Uses the [margin box](css_shapes/from_box_values#margin-box) as
        the reference box.

    [`border-box`](#border-box)

    :   Uses the [border box](css_shapes/from_box_values#border-box) as
        the reference box.

    [`padding-box`](#padding-box)

    :   Uses the [padding box](css_shapes/from_box_values#padding-box)
        as the reference box.

    [`content-box`](#content-box)

    :   Uses the [content box](css_shapes/from_box_values#content-box)
        as the reference box.

    [`fill-box`](#fill-box)

    :   Uses the object bounding box as the reference box.

    [`stroke-box`](#stroke-box)

    :   Uses the stroke bounding box as the reference box.

    [`view-box`](#view-box)

    :   Uses the nearest SVG viewport as the reference box. If a
        `viewBox` attribute is specified for the element creating the
        SVG viewport, the reference box is positioned at the origin of
        the coordinate system established by the `viewBox` attribute and
        the dimension of the size of the reference box is set to the
        width and height values of the `viewBox` attribute.

[`none`](#none)

:   No clipping path is created.

**Note:** A computed value other than `none` results in the creation of
a new [](stacking_context.md)
the same way that CSS [`opacity`](_Resources/Markup%20And%20Styling/css/opacity.md) does for values other than
`1`.

Formal definition
-----------------

  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `none`
  Applies to                         all elements; In SVG, it applies to container elements excluding the [`<defs>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/defs) element and all graphics elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to reference box when specified, otherwise border-box
  [Computed value](computed_value.md)   as specified, but with [`url()`](url.md) values made absolute
  Animation type                     yes, as specified for [`<basic-shape>`](basic-shape.md), otherwise no
  ---------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Formal syntax
-------------

```
clip-path = 
  <clip-source>                        |
  [ <basic-shape> || <geometry-box> ]  |
  none                                 

<clip-source> = 
  <url>  

<geometry-box> = 
  <shape-box>  |
  fill-box     |
  stroke-box   |
  view-box     

<url> = 
  url( <string> <url-modifier>* )  |
  src( <string> <url-modifier>* )  

<shape-box> = 
  <box>       |
  margin-box  

<box> = 
  border-box   |
  padding-box  |
  content-box  
```

Examples
--------

### Comparison of HTML and SVG

[css]

```css
html,
body {
  height: 100%;
  box-sizing: border-box;
  background: #eee;
}

.grid {
  width: 100%;
  height: 100%;
  display: flex;
  font: 1em monospace;
}

.row {
  display: flex;
  flex: 1 auto;
  flex-direction: row;
  flex-wrap: wrap;
}

.col {
  flex: 1 auto;
}

.cell {
  margin: 0.5em;
  padding: 0.5em;
  background-color: #fff;
  overflow: hidden;
  text-align: center;
  flex: 1;
}

.note {
  background: #fff3d4;
  padding: 1em;
  margin: 0.5em 0.5em 0;
  font: 0.8em sans-serif;
  text-align: left;
  white-space: nowrap;
}

.note + .row .cell {
  margin-top: 0;
}

.container {
  display: inline-block;
  border: 1px dotted grey;
  position: relative;
}

.container::before {
  content: "margin";
  position: absolute;
  top: 2px;
  left: 2px;
  font: italic 0.6em sans-serif;
}

.view-box {
  box-shadow:
    1rem 1rem 0 #efefef inset,
    -1rem -1rem 0 #efefef inset;
}

.container.view-box::after {
  content: "view-box";
  position: absolute;
  left: 1.1rem;
  top: 1.1rem;
  font: italic 0.6em sans-serif;
}

.cell span {
  display: block;
  margin-bottom: 0.5em;
}

p {
  font-family: sans-serif;
  background: #000;
  color: pink;
  margin: 2em;
  padding: 3em 1em;
  border: 1em solid pink;
  width: 6em;
}

.none {
  clip-path: none;
}
.svg {
  clip-path: url(#myPath);
}
.svg2 {
  clip-path: path(
    "M15,45 A30,30,0,0,1,75,45 A30,30,0,0,1,135,45 Q135,90,75,130 Q15,90,15,45 Z"
  );
}
.shape1 {
  clip-path: circle(25%);
}
.shape2 {
  clip-path: circle(25% at 25% 25%);
}
.shape3 {
  clip-path: fill-box circle(25% at 25% 25%);
}
.shape4 {
  clip-path: stroke-box circle(25% at 25% 25%);
}
.shape5 {
  clip-path: view-box circle(25% at 25% 25%);
}
.shape6 {
  clip-path: margin-box circle(25% at 25% 25%);
}
.shape7 {
  clip-path: border-box circle(25% at 25% 25%);
}
.shape8 {
  clip-path: padding-box circle(25% at 25% 25%);
}
.shape9 {
  clip-path: content-box circle(25% at 25% 25%);
}

.defs {
  width: 0;
  height: 0;
  margin: 0;
}

pre {
  margin-bottom: 0;
}

svg {
  margin: 1em;
  font-family: sans-serif;
  width: 192px;
  height: 192px;
}

svg rect {
  stroke: pink;
  stroke-width: 16px;
}

svg text {
  fill: pink;
  text-anchor: middle;
}

svg text.em {
  font-style: italic;
}
```

### Complete example

#### HTML

[html]

```html
<img id="clipped" src="mdn.svg" alt="MDN logo" />
<svg height="0" width="0">
  <defs>
    <clipPath id="cross">
      <rect y="110" x="137" width="90" height="90" />
      <rect x="0" y="110" width="90" height="90" />
      <rect x="137" y="0" width="90" height="90" />
      <rect x="0" y="0" width="90" height="90" />
    </clipPath>
  </defs>
</svg>

<select id="clipPath">
  <option value="none">none</option>
  <option value="circle(100px at 110px 100px)">circle</option>
  <option value="url(#cross)" selected>cross</option>
  <option value="inset(20px round 20px)">inset</option>
  <option value="path('M 0 200 L 0,110 A 110,90 0,0,1 240,100 L 200 340 z')">
    path
  </option>
</select>
```

#### CSS

[css]

```css
#clipped {
  margin-bottom: 20px;
  clip-path: url(#cross);
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------

  [CSS Masking Module Level 1\
  [\# the-clip-path]](https://drafts.fxtf.org/css-masking/#the-clip-path)

[CSS Shapes Module Level 1\
  [\#
  supported-basic-shapes]](https://drafts.csswg.org/css-shapes/#supported-basic-shapes)
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

`clip-path`

5523

79

12Only supports clip paths defined by `url()`.

3.5

10Only supports clip paths defined by `url()`.

4215

9.17

554.4

5525

4

4214

9.37

6.01.5

`animations`

55

79

49

No

42

No

55

55

49

42

No

6.0

`basic_shape`

23

79

54

No

15

7

4.4

25

54

14

7

1.5

`fill_and_stroke_box`

No

No

51This value was supported before Firefox 51, but as an alias to
`border-box`.

No

No

13.1

No

No

51This value was supported before Firefox 51, but as an alias to
`border-box`.

No

13.4

No

`html`

23

79

3.5

No

15

7

4.4

25

4

14

7

1.5

`path`

88

88

71

No

74

13.110

88

88

79

63

1310

15.0

`svg`

23

12

52

10

15

7

4.4

25

52

14

7

1.5

See also
--------

- [Shapes in clipping and masking -- and how to use
    them](https://hacks.mozilla.org/2017/06/css-shapes-clipping-and-masking/)
- CSS properties: [`mask`](mask.md), [`filter`](filter.md)
- [Applying SVG effects to HTML
    content](https://developer.mozilla.org/en-US/docs/Web/SVG/Applying_SVG_effects_to_HTML_content)
- SVG attributes:
  - `clip-path`
  - `clip-rule`

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path>

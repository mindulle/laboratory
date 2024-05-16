polygon()
=========

The `polygon()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
function is one of the [`<basic-shape>`](basic-shape.md) [](css_types.md). It\'s used to draw a
[polygon](https://en.wikipedia.org/wiki/Polygon) by providing one or
more pairs of coordinates, each of which represents a vertex of the
shape.

Try it
------

Syntax
------

[css]

```
/* Specified as coordinate list */
/* polygon(<length-percentage> <length-percentage>, ... )*/
polygon(50% 2.4%, 34.5% 33.8%, 0% 38.8%, 25% 63.1%, 19.1% 97.6%)
polygon(0px 0px, 200px 100px, 0px 200px)
polygon(0% 0px, 100% 100px, 0px 100%)
polygon(0 0, 50% 1rem, 100% 2vw, calc(100% - 20px) 100%, 0 100%)

/* Specified as coordinate list and fill rule*/
/* polygon(<fill-rule> <length-percentage> <length-percentage>, ... )*/
```css
polygon(evenodd, 0% 0%, 50% 50%, 0% 100%)
```

### Parameters

[`<fill-rule>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/fill-rule) [Optional]

:   An optional value of `nonzero` (the default when omitted) or
    `evenodd`, which specifies the filling rule.

[`<length-percentage>`](length-percentage.md)

:   Each vertex of the polygon is represented with a pair of
    `<length-percentage>` values, which give the coordinates of the
    vertex relative to the shape\'s [](basic_shapes.md#the_reference_box).

### Return value

Returns a [`<basic-shape>`](basic-shape.md) value.

Formal syntax
-------------

Error: could not find syntax for this item

Examples
--------

### Setting a polygon for shape-outside

In this example a shape is created for text to follow using the
[`shape-outside`](shape-outside.md) property.

[html]

```html
<div class="box">
  <div class="shape"></div>
  <p>
    One November night in the year 1782, so the story runs, two brothers sat
    over their winter fire in the little French town of Annonay, watching the
    grey smoke-wreaths from the hearth curl up the wide chimney. Their names
    were Stephen and Joseph Montgolfier, they were papermakers by trade, and
    were noted as possessing thoughtful minds and a deep interest in all
    scientific knowledge and new discovery. Before that night—a memorable night,
    as it was to prove—hundreds of millions of people had watched the rising
    smoke-wreaths of their fires without drawing any special inspiration from
    the fact.
  </p>
</div>
```

[css]

```
.box {
  width: 250px;
}

.shape {
  float: left;
  shape-outside: polygon(
    0 5%,
    15% 12%,
    30% 15%,
    40% 26%,
    45% 35%,
    45% 45%,
    40% 55%,
    10% 90%,
    10% 98%,
    8% 100%,
    0 100%
  );
  width: 300px;
  height: 320px;
}

p {
  font-size: 0.9rem;
}
```

Specifications
--------------

  ---------------------------------------------------------------------------------------------------------

```css
Specification
  ---------------------------------------------------------------------------------------------------------

  [CSS Shapes Module Level 1\
  [\#
  funcdef-basic-shape-polygon]](https://drafts.csswg.org/css-shapes/#funcdef-basic-shape-polygon)

  ---------------------------------------------------------------------------------------------------------

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

`polygon`

37

79

54

No

24

10.1

37

37

54

24

10.3

3.0

See also 
--------

- Properties that use this data type: [`clip-path`](../clip-path),
    [`shape-outside`](../shape-outside)
- [Guide to Basic Shapes](../css_shapes/basic_shapes)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/basic-shape/polygon>

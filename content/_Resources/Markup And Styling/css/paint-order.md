paint-order
===========

The `paint-order`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property lets
you control the order in which the fill and stroke (and painting
markers) of text content and shapes are drawn.

Syntax
------

[css]

```css
/* Normal */
paint-order: normal;

/* Single values */
paint-order: stroke; /* draw the stroke first, then fill and markers */
paint-order: markers; /* draw the markers first, then fill and stroke */

/* Multiple values */
paint-order: stroke fill; /* draw the stroke first, then the fill, then the markers */
paint-order: markers stroke fill; /* draw markers, then stroke, then fill */

/* Global values */
paint-order: inherit;
paint-order: initial;
paint-order: revert;
paint-order: revert-layer;
paint-order: unset;
```

If no value is specified, the default paint order is `fill`, `stroke`,
`markers`.

When one value is specified, that one is painted first, followed by the
other two in their default order relative to one another. When two
values are specified, they will be painted in the order they are
specified in, followed by the unspecified one.

**Note:** In the case of this property, markers are only appropriate
when drawing SVG shapes involving the use of the `marker-*` properties
(e.g.
[`marker-start`](https://developer.mozilla.org/en-US/docs/Web/SVG/Attribute/marker-start))
and
[`<marker>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/marker)
element. They do not apply to HTML text, so in that case, you can only
determine the order of `stroke` and `fill`.

### Values

[`normal`](#normal)

:   Paint the different items in normal paint order.

[`stroke`](#sect2), `fill`, `markers`

:   Specify some or all of these values in the order you want them to be
    painted in.

Formal definition
-----------------

  ---------------------------------- ---------------
  [Initial value](initial_value.md)     `normal`
  Applies to                         text elements
  [Inherited](inheritance.md)           yes
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ---------------

Formal syntax
-------------

```
paint-order = 
  normal                         |
  [ fill || stroke || markers ]  
```

Examples
--------

### Reversing the paint order of stroke and fill

#### SVG

[html]

```html
<svg xmlns="http://www.w3.org/2000/svg" width="400" height="200">
  <text x="10" y="75">stroke in front</text>
  <text x="10" y="150" class="stroke-behind">stroke behind</text>
</svg>
```

#### CSS

[css]

```css
text {
  font-family: sans-serif;
  font-size: 50px;
  font-weight: bold;
  fill: black;
  stroke: red;
  stroke-width: 4px;
}

.stroke-behind {
  paint-order: stroke fill;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------

  [Scalable Vector Graphics (SVG) 2\
  [\#
  PaintOrder]](https://svgwg.org/svg2-draft/painting.html#PaintOrder)

  -----------------------------------------------------------------------------

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

`paint-order`

35

17

60

No

22

8

37

35

60

22

8

3.0

See also
--------

- [CSS Tricks:
    paint-order](https://css-tricks.com/almanac/properties/p/paint-order/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/paint-order>

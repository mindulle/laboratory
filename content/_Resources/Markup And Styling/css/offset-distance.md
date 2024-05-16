offset-distance
===============

The `offset-distance` CSS property specifies a position along an
[`offset-path`](offset-path.md) for an element to be placed.

Try it
------

Syntax
------

[css]

```css
/* Default value */
offset-distance: 0;

/* the middle of the offset-path */
offset-distance: 50%;

/* a fixed length positioned along the path */
offset-distance: 40px;

/* Global values */
offset-distance: inherit;
offset-distance: initial;
offset-distance: revert;
offset-distance: revert-layer;
offset-distance: unset;
```

`<length-percentage>`

:   A length that specifies how far the element is along the path
    (defined with [`offset-path`](offset-path.md)).

    100% represents the total length of the path (when the `offset-path`
    is defined as a basic shape or `path()`).

Formal definition
-----------------

  ---------------------------------- -------------------------------------------------------------------------------------
  [Initial value](initial_value.md)     `0`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  Percentages                        refer to the total path length
  [Computed value](computed_value.md)   for [`<length>`](length.md) the absolute value, otherwise a percentage
  Animation type                     a [length](length.md#interpolation), [percentage](percentage.md#interpolation) or calc();
  ---------------------------------- -------------------------------------------------------------------------------------

Formal syntax
-------------

```
offset-distance = 
  <length-percentage>  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Examples
--------

### Using offset-distance in an animation

The motion aspect in CSS Motion Path typically comes from animating the
`offset-distance` property. If you want to animate an element along its
full path, you would define its [`offset-path`](offset-path.md) and then
set up an animation that takes the `offset-distance` from `0%` to
`100%`.

#### HTML

[html]

```html
<div id="motion-demo"></div>
```

#### CSS

[css]

```css
#motion-demo {
  offset-path: path("M20,20 C20,100 200,0 200,100");
  animation: move 3000ms infinite alternate ease-in-out;
  width: 40px;
  height: 40px;
  background: cyan;
}

@keyframes move {
  0% {
    offset-distance: 0%;
  }
  100% {
    offset-distance: 100%;
  }
}
```

#### Result

Specifications
--------------

  ----------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------

  [Motion Path Module Level 1\
  [\#
  offset-distance-property]](https://drafts.fxtf.org/motion/#offset-distance-property)

  ----------------------------------------------------------------------------------------------

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

`offset-distance`

5546

7979

72

No

4233

16

5546

5546

79

4233

16

6.05.0

See also
--------

- [`offset`](offset.md)
- [`offset-anchor`](offset-anchor.md)
- [`offset-path`](offset-path.md)
- [`offset-position`](offset-position.md)
- [`offset-rotate`](offset-rotate.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/offset-distance>

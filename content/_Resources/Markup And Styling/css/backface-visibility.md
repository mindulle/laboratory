backface-visibility
===================

The `backface-visibility`
[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets
whether the back face of an element is visible when turned towards the
user.

Try it
------

An element\'s back face is a mirror image of its front face. Though
invisible in 2D, the back face can become visible when a transformation
causes the element to be rotated in 3D space. (This property has no
effect on 2D transforms, which have no perspective.)

Syntax
------

[css]

```css
/* Keyword values */
backface-visibility: visible;
backface-visibility: hidden;

/* Global values */
backface-visibility: inherit;
backface-visibility: initial;
backface-visibility: revert;
backface-visibility: revert-layer;
backface-visibility: unset;
```

The `backface-visibility` property is specified as one of the keywords
listed below.

### Values

[`visible`](#visible)

:   The back face is visible when turned towards the user.

[`hidden`](#hidden)

:   The back face is hidden, effectively making the element invisible
    when turned away from the user.

Formal definition
-----------------

  ---------------------------------- ------------------------
  [Initial value](initial_value.md)     `visible`
  Applies to                         transformable elements
  [Inherited](inheritance.md)           no
  [Computed value](computed_value.md)   as specified
  Animation type                     discrete
  ---------------------------------- ------------------------

Formal syntax
-------------

```
backface-visibility = 
  visible  |
  hidden   
```

Examples
--------

### Cube with transparent and opaque faces

This example shows a cube with transparent faces, and one with opaque
faces.

#### HTML

[html]

```html
<table>
  <tr>
    <th><code>backface-visibility: visible;</code></th>
    <th><code>backface-visibility: hidden;</code></th>
  </tr>
  <tr>
    <td>
      <div class="container">
        <div class="cube showbf">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
      <p>
        Since all faces are partially transparent, the back faces (2, 4, 5) are
        visible through the front faces (1, 3, 6).
      </p>
    </td>
    <td>
      <div class="container">
        <div class="cube hidebf">
          <div class="face front">1</div>
          <div class="face back">2</div>
          <div class="face right">3</div>
          <div class="face left">4</div>
          <div class="face top">5</div>
          <div class="face bottom">6</div>
        </div>
      </div>
      <p>The three back faces (2, 4, 5) are hidden.</p>
    </td>
  </tr>
</table>
```

#### CSS

[css]

```css
/* Classes that will show or hide the
   three back faces of the "cube" */
.showbf div {
  backface-visibility: visible;
}

.hidebf div {
  backface-visibility: hidden;
}

/* Define the container div, the cube div, and a generic face */
.container {
  width: 150px;
  height: 150px;
  margin: 75px 0 0 75px;
  border: none;
}

.cube {
  width: 100%;
  height: 100%;
  perspective: 550px;
  perspective-origin: 150% 150%;
  transform-style: preserve-3d;
}

.face {
  display: block;
  position: absolute;
  width: 100px;
  height: 100px;
  border: none;
  line-height: 100px;
  font-family: sans-serif;
  font-size: 60px;
  color: white;
  text-align: center;
}

/* Define each face based on direction */
.front {
  background: rgba(0, 0, 0, 0.3);
  transform: translateZ(50px);
}

.back {
  background: rgba(0, 255, 0, 1);
  color: black;
  transform: rotateY(180deg) translateZ(50px);
}

.right {
  background: rgba(196, 0, 0, 0.7);
  transform: rotateY(90deg) translateZ(50px);
}

.left {
  background: rgba(0, 0, 196, 0.7);
  transform: rotateY(-90deg) translateZ(50px);
}

.top {
  background: rgba(196, 196, 0, 0.7);
  transform: rotateX(90deg) translateZ(50px);
}

.bottom {
  background: rgba(196, 0, 196, 0.7);
  transform: rotateX(-90deg) translateZ(50px);
}

/* Make the table a little nicer */
th,
p,
td {
  background-color: #eeeeee;
  margin: 0px;
  padding: 6px;
  font-family: sans-serif;
  text-align: left;
}
```

#### Result

Specifications
--------------

  -----------------------------------------------------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------------------------------------------------

  [CSS Transforms Module Level 2\
  [\#
  backface-visibility-property]](https://drafts.csswg.org/css-transforms-2/#backface-visibility-property)

  -----------------------------------------------------------------------------------------------------------------

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

`backface-visibility`

3612

1212

491610

10

2315

15.45.1

373

3618

491610

2414

15.45

3.01.0

See also
--------

- [Using CSS transforms](using_css_transforms.md)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility>

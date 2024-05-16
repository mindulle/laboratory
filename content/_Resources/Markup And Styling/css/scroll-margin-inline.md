scroll-margin-inline
====================

The `scroll-margin-inline` [shorthand property](shorthand_properties.md)
sets the scroll margins of an element in the inline dimension.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`scroll-margin-inline-end`](scroll-margin-inline-end.md)
- [`scroll-margin-inline-start`](scroll-margin-inline-start.md)

Syntax
------

[css]

```css
/* <length> values */
scroll-margin-inline: 10px;
scroll-margin-inline: 1em 0.5em;

/* Global values */
scroll-margin-inline: inherit;
scroll-margin-inline: initial;
scroll-margin-inline: revert;
scroll-margin-inline: revert-layer;
scroll-margin-inline: unset;
```

### Values

[`<length>`](length.md)

:   An outset from the corresponding edge of the scroll container.

Description
-----------

The scroll-margin values represent outsets defining the scroll snap area
that is used for snapping this box to the snapport. The scroll snap area
is determined by taking the transformed border box, finding its
rectangular bounding box (axis-aligned in the scroll container\'s
coordinate space), then adding the specified outsets.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-margin-inline-start.md): |
|                                   |     `0`                           |
|                                   | -   [](scroll-margin-inline-end.md): |
|                                   |     `0`                           |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-margin-inline-start.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-margin-inline-end.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | by computed value type            |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
scroll-margin-inline = 
  <length>  
```

Examples
--------

### Simple demonstration

This example implements something very similar to the interactive
example above, except that here we\'ll explain to you how it\'s
implemented.

The aim here is to create four horizontally-scrolling blocks, the second
and third of which snap into place, near but not quite at the right of
each block.

#### HTML

The HTML that represents the blocks is very simple:

[html]

```html
<div class="scroller">
  <div>1</div>
  <div>2</div>
  <div>3</div>
  <div>4</div>
</div>
```

#### CSS

Let\'s walk through the CSS. The outer container is styled like this:

[css]

```css
.scroller {
  text-align: left;
  width: 250px;
  height: 250px;
  overflow-x: scroll;
  display: flex;
  box-sizing: border-box;
  border: 1px solid #000;
  scroll-snap-type: x mandatory;
}
```

The main parts relevant to the scroll snapping are `overflow-x: scroll`,
which makes sure the contents will scroll and not be hidden, and
`scroll-snap-type: x mandatory`, which dictates that scroll snapping
must occur along the horizontal axis, and the scrolling will always come
to rest on a snap point.

The child elements are styled as follows:

[css]

```css
.scroller > div {
  flex: 0 0 250px;
  width: 250px;
  background-color: #663399;
  color: #fff;
  font-size: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  scroll-snap-align: end;
}

.scroller > div:nth-child(2n) {
  background-color: #fff;
  color: #663399;
}
```

The most relevant part here is `scroll-snap-align: end`, which specifies
that the right-hand edges (the \"ends\" along the x axis, in our case)
are the designated snap points.

Last of all we specify the scroll margin values, a different one for the
second and third child elements:

[css]

```css
.scroller > div:nth-child(2) {
  scroll-margin-inline: 1rem;
}

.scroller > div:nth-child(3) {
  scroll-margin-inline: 2rem;
}
```

This means that when scrolling past the middle child elements, the
scrolling will snap to `1rem` outside the inline end edge of the second
`<div>`, and `2rems` outside the inline end edge of the third `<div>`.

**Note:** Here we are setting `scroll-margin` on the start *and* end of
the inline axis (x in our case), but only the end edge is really
relevant. It would work just as well here to only set a scroll margin on
that one edge, for example with `scroll-margin-inline: 0 1rem`, or
`scroll-margin-inline-end: 1rem`.

#### Result

Try it for yourself:

Specifications
--------------

  ----------------------------------------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  propdef-scroll-margin-inline]](https://drafts.csswg.org/css-scroll-snap/#propdef-scroll-margin-inline)

  ----------------------------------------------------------------------------------------------------------------

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

`scroll-margin-inline`

69

79

68

No

56

15

69

69

68

48

15

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-inline>

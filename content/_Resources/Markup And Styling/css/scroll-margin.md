scroll-margin
=============

The `scroll-margin` [shorthand property](shorthand_properties.md) sets all
of the scroll margins of an element at once, assigning values much like
the [`margin`](margin.md) property does for margins of an element.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`scroll-margin-bottom`](scroll-margin-bottom.md)
- [`scroll-margin-left`](scroll-margin-left.md)
- [`scroll-margin-right`](scroll-margin-right.md)
- [`scroll-margin-top`](scroll-margin-top.md)

Syntax
------

[css]

```css
/* <length> values */
scroll-margin: 10px;
scroll-margin: 1em 0.5em 1em 1em;

/* Global values */
scroll-margin: inherit;
scroll-margin: initial;
scroll-margin: revert;
scroll-margin: revert-layer;
scroll-margin: unset;
```

### Values

[`<length>`](length.md)

:   An outset from the corresponding edge of the scroll container.

Description
-----------

You can see the effect of `scroll-margin` by scrolling to a point
partway between two of the \"pages\" of the example\'s content. The
value specified for `scroll-margin` determines how much of the page
that\'s primarily outside the snapport should remain visible.

Thus, the `scroll-margin` values represent outsets defining the scroll
snap area that is used for snapping this box to the snapport. The scroll
snap area is determined by taking the transformed border box, finding
its rectangular bounding box (axis-aligned in the scroll container\'s
coordinate space), then adding the specified outsets.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-margin-bottom.md): |
|                                   |     `0`                           |
|                                   | -   [](scroll-margin-left.md): |
|                                   |     `0`                           |
|                                   | -   [](scroll-margin-right.md): |
|                                   |     `0`                           |
|                                   | -   [](scroll-margin-top.md): |
|                                   |     `0`                           |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-margin-bottom.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-margin-left.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-margin-right.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-margin-top.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | by computed value type            |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
scroll-margin = 
  <length>  
```

Examples
--------

### Simple demonstration

This example implements something very similar to the interactive
example above, except that here we\'ll explain to you how it\'s
implemented.

The aim here is to create four horizontally-scrolling blocks, the second
and third of which snap into place, near but not quite at the left of
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
  scroll-snap-align: start;
}

.scroller > div:nth-child(2n) {
  background-color: #fff;
  color: #663399;
}
```

The most relevant part here is `scroll-snap-align: start`, which
specifies that the left-hand edges (the \"starts\" along the x axis, in
our case) are the designated snap points.

Last of all we specify the scroll margin-values, a different one for the
second and third child elements:

[css]

```css
.scroller > div:nth-child(2) {
  scroll-margin: 1rem;
}

.scroller > div:nth-child(3) {
  scroll-margin: 2rem;
}
```

This means that when scrolling past the middle child elements, the
scrolling will snap to `1rem` outside the left edge of the second
`<div>`, and `2rems` outside the left edge of the third `<div>`.

**Note:** Here we are setting `scroll-margin` on all sides at once, but
only the start edge is really relevant. It would work just as well here
to only set a scroll margin on that one edge, for example with
`scroll-margin-inline-start: 1rem`, or `scroll-margin: 0 0 0 1rem`.

#### Result

Try it for yourself:

Specifications
--------------

  ----------------------------------------------------------------------------------

Specification
  ----------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  scroll-margin]](https://drafts.csswg.org/css-scroll-snap/#scroll-margin)

  ----------------------------------------------------------------------------------

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

`scroll-margin`

69

79

90

68--90The `scroll-margin` property can cause an element\'s visibility to
be incorrectly calculated for `element.focus()`. See [bug
1708303](https://bugzil.la/1708303).

No

56

14.1

11Before version 14.1, scroll margin is not applied for scrolls to
fragment target or `scrollIntoView()`, see [bug
189265](https://webkit.org/b/189265).

69

69

90

68--90The `scroll-margin` property can cause an element\'s visibility to
be incorrectly calculated for `element.focus()`. See [bug
1708303](https://bugzil.la/1708303).

48

14.5

11Before version 14.5, scroll margin is not applied for scrolls to
fragment target or `scrollIntoView()`, see [bug
189265](https://webkit.org/b/189265).

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin>

scroll-margin-block
===================

The `scroll-margin-block` [shorthand property](shorthand_properties.md)
sets the scroll margins of an element in the block dimension.

Try it
------

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`scroll-margin-block-end`](scroll-margin-block-end.md)
- [`scroll-margin-block-start`](scroll-margin-block-start.md)

Syntax
------

[css]

```css
/* <length> values */
scroll-margin-block: 10px;
scroll-margin-block: 1em 0.5em;

/* Global values */
scroll-margin-block: inherit;
scroll-margin-block: initial;
scroll-margin-block: revert;
scroll-margin-block: revert-layer;
scroll-margin-block: unset;
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
|                                   | -   [](scroll-margin-block-start.md): |
|                                   |     `0`                           |
|                                   | -   [](scroll-margin-block-end.md): |
|                                   |     `0`                           |
+-----------------------------------+-----------------------------------+
| Applies to                        | all elements                      |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-margin-block-start.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-margin-block-end.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | by computed value type            |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
scroll-margin-block = 
  <length>  
```

Specifications
--------------

  --------------------------------------------------------------------------------------------------------------

Specification
  --------------------------------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  propdef-scroll-margin-block]](https://drafts.csswg.org/css-scroll-snap/#propdef-scroll-margin-block)

  --------------------------------------------------------------------------------------------------------------

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

`scroll-margin-block`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-margin-block>

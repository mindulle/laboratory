scroll-padding
==============

The `scroll-padding` [shorthand property](shorthand_properties.md) sets
scroll padding on all sides of an element at once, much like the
[`padding`](padding.md) property does for padding on an element.

Try it
------

The `scroll-padding-*` properties define offsets for the *optimal
viewing region* of the scrollport: the region used as the target region
for placing things in view of the user. This allows the author to
exclude regions of the scrollport that are obscured by other content
(such as fixed-positioned toolbars or sidebars), or to put more
breathing room between a targeted element and the edges of the
scrollport.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`scroll-padding-bottom`](scroll-padding-bottom.md)
- [`scroll-padding-left`](scroll-padding-left.md)
- [`scroll-padding-right`](scroll-padding-right.md)
- [`scroll-padding-top`](scroll-padding-top.md)

Syntax
------

[css]

```css
/* Keyword values */
scroll-padding: auto;

/* <length> values */
scroll-padding: 10px;
scroll-padding: 1em 0.5em 1em 1em;
scroll-padding: 10%;

/* Global values */
scroll-padding: inherit;
scroll-padding: initial;
scroll-padding: revert;
scroll-padding: revert-layer;
scroll-padding: unset;
```

### Values

[`<length-percentage>`](length-percentage.md)

:   An inwards offset from the corresponding edge of the scrollport, as
    a valid [`<length>`](length.md) or a [`<percentage>`](percentage.md).

[`auto`](#auto)

:   The offset is determined by the user agent. This will generally be
    `0px`, but the user agent is free to detect and do something else if
    a non-zero value is more appropriate.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-padding-bottom.md): |
|                                   |     `auto`                        |
|                                   | -   [](scroll-padding-left.md): |
|                                   |     `auto`                        |
|                                   | -   [](scroll-padding-right.md): |
|                                   |     `auto`                        |
|                                   | -   [](scroll-padding-top.md): |
|                                   |     `auto`                        |
+-----------------------------------+-----------------------------------+
| Applies to                        | scroll containers                 |
+-----------------------------------+-----------------------------------+
| [Inherited](inheritance.md)          | no                                |
+-----------------------------------+-----------------------------------+
| Percentages                       | relative to the scroll            |
|                                   | container\'s scrollport           |
+-----------------------------------+-----------------------------------+
| [Computed value](computed_value.md)  | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-padding-bottom.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-padding-left.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-padding-right.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-padding-top.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | by computed value type            |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
scroll-padding = 
  [ auto | <length-percentage [0,∞]> ]  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Specifications
--------------

  ------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  scroll-padding]](https://drafts.csswg.org/css-scroll-snap/#scroll-padding)

  ------------------------------------------------------------------------------------

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

`scroll-padding`

69

79

68

No

56

14.1

11--14.1Scroll padding is not applied for scrolls to fragment target or
`scrollIntoView()`, see [bug 179379](https://webkit.org/b/179379).

69

69

68

48

14.5

11--14.5Scroll padding is not applied for scrolls to fragment target or
`scrollIntoView()`, see [bug 179379](https://webkit.org/b/179379).

10.0

See also
--------

- [CSS scroll snap](css_scroll_snap.md)
- [Well-controlled scrolling with CSS scroll
    snap](https://web.dev/css-scroll-snap/)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding>

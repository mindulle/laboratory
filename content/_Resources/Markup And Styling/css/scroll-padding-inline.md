scroll-padding-inline
=====================

The `scroll-padding-inline` [shorthand property](shorthand_properties.md)
sets the scroll padding of an element in the inline dimension.

Try it
------

The scroll-padding properties define offsets for the *optimal viewing
region* of the scrollport: the region used as the target region for
placing things in view of the user. This allows the author to exclude
regions of the scrollport that are obscured by other content (such as
fixed-positioned toolbars or sidebars) or to put more breathing room
between a targeted element and the edges of the scrollport.

Constituent properties
----------------------

This property is a shorthand for the following CSS properties:

- [`scroll-padding-inline-end`](scroll-padding-inline-end.md)
- [`scroll-padding-inline-start`](scroll-padding-inline-start.md)

Syntax
------

[css]

```css
/* Keyword values */
scroll-padding-inline: auto;

/* <length> values */
scroll-padding-inline: 10px;
scroll-padding-inline: 1em 0.5em;
scroll-padding-inline: 10%;

/* Global values */
scroll-padding-inline: inherit;
scroll-padding-inline: initial;
scroll-padding-inline: revert;
scroll-padding-inline: revert-layer;
scroll-padding-inline: unset;
```

### Values

[`<length-percentage>`](#length-percentage)

:   An inwards offset from the corresponding edge of the scrollport, as
    a valid length or a percentage.

[`auto`](#auto)

:   The offset is determined by the user agent. This will generally be
    0px, but a user agent is able to detect and do something else if a
    non-zero value is more appropriate.

Formal definition
-----------------

+-----------------------------------+-----------------------------------+
| [Initial value](initial_value.md)    | as each of the properties of the  |
|                                   | shorthand:\                       |
|                                   |                                   |
|                                   | -   [](scroll-padding-inline-start.md): |
|                                   |     `auto`                        |
|                                   | -   [](scroll-padding-inline-end.md): |
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
|                                   | -   [](scroll-padding-inline-start.md): |
|                                   |     as specified                  |
|                                   | -   [](scroll-padding-inline-end.md): |
|                                   |     as specified                  |
+-----------------------------------+-----------------------------------+
| Animation type                    | by computed value type            |
+-----------------------------------+-----------------------------------+

Formal syntax
-------------

```
scroll-padding-inline = 
  [ auto | <length-percentage [0,∞]> ]  

<length-percentage> = 
  <length>      |
  <percentage>  
```

Specifications
--------------

  ------------------------------------------------------------------------------------------------------------------

Specification
  ------------------------------------------------------------------------------------------------------------------

  [CSS Scroll Snap Module Level 1\
  [\#
  propdef-scroll-padding-inline]](https://drafts.csswg.org/css-scroll-snap/#propdef-scroll-padding-inline)

  ------------------------------------------------------------------------------------------------------------------

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

`scroll-padding-inline`

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
https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-padding-inline>

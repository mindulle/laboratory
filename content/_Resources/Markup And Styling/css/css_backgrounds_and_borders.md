CSS backgrounds and borders
===========================

The **CSS backgrounds and borders** module provides properties for
adding borders, rounded corners, and box shadows to elements.

You can add different types of border styles, including borders made of
images of any image type, from raster images to CSS gradients. Borders
can be square or rounded, and a different radius can be set for each
corner. Elements can be rounded whether or not they have a visible
border.

Box shadows include inset and outset shadow, single or multiple shadows,
and solid or allowed to fade to transparent. An outer box-shadow casts a
shadow as if the border-box of the element were opaque. An inner
box-shadow casts a shadow as if everything outside the padding edge were
opaque. The shadow can be solid or include a spread distance with the
shadow color transitioning to transparent.

The properties in this module also let you define whether cells inside a
[`<table>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
should have shared or separate borders.

### Backgrounds, borders, and box shadows in action

This sample of borders, backgrounds, and box shadows consists of
centered background images made of linear and radial gradients. A series
of box shadows make the border appear to \"pop\". The element on the
left has a border image set. The element on the right has a rounded
dotted border.

The background images are defined with
[`background-image`](background-image.md). The images are centered with
[`background-position`](background-position.md). Different values of the
[`background-clip`](background-clip.md) property for the multiple
background images are used to make the background images stay within the
content box. The background color gets clipped to the padding box
preventing the background from appearing through the transparent
sections for the [`border-image`](border-image.md) and the
[`dotted`](border-style.md) [`border`](border.md). The rounded corners in the
element on the right are created using the
[`border-radius`](border-radius.md) property. A single
[`box-shadow`](box-shadow.md) declaration is used to set all the shadows,
both inset and outset.

To see the code for this sample, [view the source on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/backgrounds.html).

Reference
---------

### Properties

- [`background-attachment`](background-attachment.md)
- [`background-clip`](background-clip.md)
- [`background-color`](background-color.md)
- [`background-image`](background-image.md)
- [`background-origin`](background-origin.md)
- [`background-position`](background-position.md)
- [`background-repeat`](background-repeat.md)
- [`background-size`](background-size.md)
- [`background`](background.md) shorthand
- [`background-position-x`](background-position-x.md)
    [Experimental]
- [`background-position-y`](background-position-y.md)
    [Experimental]
- [`background-position-inline`]
    [Experimental]
- [`background-position-block`]
    [Experimental]
- [`border-bottom-color`](border-bottom-color.md)
- [`border-bottom-style`](border-bottom-style.md)
- [`border-bottom-width`](border-bottom-width.md)
- [`border-bottom`](border-bottom.md) shorthand
- [`border-left-color`](border-left-color.md)
- [`border-left-style`](border-left-style.md)
- [`border-left-width`](border-left-width.md)
- [`border-left`](border-left.md) shorthand
- [`border-right-color`](border-right-color.md)
- [`border-right-style`](border-right-style.md)
- [`border-right-width`](border-right-width.md)
- [`border-right`](border-right.md) shorthand
- [`border-top-color`](border-top-color.md)
- [`border-top-style`](border-top-style.md)
- [`border-top-width`](border-top-width.md)
- [`border-top`](border-top.md) shorthand
- [`border-color`](border-color.md) shorthand
- [`border-style`](border-style.md) shorthand
- [`border-width`](border-width.md) shorthand
- [`border`](border.md) shorthand
- [`border-collapse`](border-collapse.md)
- [`border-bottom-left-radius`](border-bottom-left-radius.md)
- [`border-bottom-right-radius`](border-bottom-right-radius.md)
- [`border-top-left-radius`](border-top-left-radius.md)
- [`border-top-right-radius`](border-top-right-radius.md)
- [`border-radius`](border-radius.md) shorthand
- [`border-image-outset`](border-image-outset.md)
- [`border-image-repeat`](border-image-repeat.md)
- [`border-image-slice`](border-image-slice.md)
- [`border-image-source`](border-image-source.md)
- [`border-image-width`](border-image-width.md)
- [`border-image`](border-image.md) shorthand
- [`box-shadow`](box-shadow.md)

### Data types

- [`line-type`] enumerated type

Guides
------

[Learn CSS: background and borders](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Backgrounds_and_borders)

:   Explains how to implement decorative images using CSS background
    images.

[Using multiple backgrounds](using_multiple_backgrounds.md)

:   Explains how to set one or more backgrounds on an element.

[Resizing background images](resizing_background_images.md)

:   Describes how to change the size and repeating behavior of
    background images.

[Learn CSS: the box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)

:   Explains how borders, along with other box model properties, impact
    the CSS box model.

[Using CSS gradients](using_css_gradients.md)

:   Explains how to create CSS gradient background images.

Related concepts
----------------

- [`border-block-end-color`](border-block-end-color.md) property
- [`border-block-start-color`](border-block-start-color.md) property
- [`border-inline-end-color`](border-inline-end-color.md) property
- [`border-inline-start-color`](border-inline-start-color.md) property
- [`border-block-end-style`](border-block-end-style.md) property
- [`border-block-start-style`](border-block-start-style.md) property
- [`border-inline-end-style`](border-inline-end-style.md) property
- [`border-inline-start-style`](border-inline-start-style.md) property
- [`border-block-end-width`](border-block-end-width.md) property
- [`border-block-start-width`](border-block-start-width.md) property
- [`border-inline-end-width`](border-inline-end-width.md) property
- [`border-inline-start-width`](border-inline-start-width.md) property
- [`border-start-start-radius`](border-start-start-radius.md) property
- [`border-start-end-radius`](border-start-end-radius.md) property
- [`border-end-start-radius`](border-end-start-radius.md) property
- [`border-end-end-radius`](border-end-end-radius.md) property
- [`box-sizing`](box-sizing.md) property
- [`box-decoration-break`](box-decoration-break.md) property
- [`text-shadow`](text-shadow.md) property
- [`url()`](url.md) CSS function
- [`<color>`](_Resources/Markup%20And%20Styling/css/color.md) data type
- [`<image>`](_Resources/Markup%20And%20Styling/css/image.md) data type
- [`<position>`](position.md) data type
- [`currentcolor`](color_value.md#currentcolor_keyword) keyword

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Backgrounds and Borders Module Level 3\
  ](https://drafts.csswg.org/css-backgrounds/)

  -----------------------------------------------------------------------

See also
--------

- Interactive tools that let you visually create borders images,
    rounded corners, and box shadows:
  - [](border-image_generator.md)
  - [](border-radius_generator.md)
  - [](box-shadow_generator.md)
- [](applying_color.md), including for borders.
- The [`drop-shadow()`](drop-shadow.md) filter function
    that applies a drop shadow effect to the input image. The function
    is used by the [`filter`](filter.md) and
    [`backdrop-filter`](backdrop-filter.md) properties.

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_backgrounds_and_borders>

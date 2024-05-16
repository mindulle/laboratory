CSS compositing and blending
============================

The **CSS compositing and blending** module defines how an element\'s
background layers can be blended together, how an element can be blended
with its container, and whether the element must create a new [](stacking_context.md).

The properties in this CSS module can be used to define the blending
mode that should be used, if any, to blend an element\'s background
images and colors into a single background image. This module provides
16 blending modes. You can also define how an element\'s borders,
background, and content, including text, emojis, and images, should be
blended with the background of its container.

### Compositing and blending in action

In this example, each box has a border, two striped background images,
and a solid color background. The common background for all the boxes
contains a pattern of circles. The three boxes in the second row are set
to blend with the background of the container.

Notice how the background, border, and the content are all impacted as a
result of the blending. To see the code for this sample, [view the
source on
GitHub](https://github.com/mdn/css-examples/blob/main/modules/compositing.html).

Reference
---------

### Properties

- [`background-blend-mode`](background-blend-mode.md)
- [`isolation`](isolation.md)
- [`mix-blend-mode`](mix-blend-mode.md)

Related concepts
----------------

- [`<blend-mode>`](blend-mode.md) data type
- [`backdrop-filter`](backdrop-filter.md) CSS property
- [`filter`](filter.md) CSS property
- [`mask-composite`](mask-composite.md) CSS property
- [`background-color`](background-color.md) CSS property
- [`background-image`](background-image.md) CSS property
- [stacking
    context](https://developer.mozilla.org/en-US/docs/Glossary/Stacking_context)
    glossary term
- [`<feBlend>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feBlend)
    SVG filter primitive
- [`<feComposite>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/feComposite)
    SVG filter primitive

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [Compositing and Blending Level 2\
  ](https://drafts.fxtf.org/compositing/)

[Compositing and Blending Level 1\
  ](https://www.w3.org/TR/compositing-1/)
  -----------------------------------------------------------------------

See also
--------

- Properties in the [CSS filter effects](css_filter_effects.md) module
    enable applying filters effects, such as blurring and changing color
    intensity, to images, backgrounds, and borders.
- [Compositing And Blending In
    CSS](https://www.sarasoueidan.com/blog/compositing-and-blending-in-css/) (2015)
- [Editing Images in CSS: Blend
    Modes](https://code.tutsplus.com/tutorials/editing-images-in-css-blend-modes--cms-26058) (2022)
- [web.dev: blend
    modes](https://web.dev/learn/css/blend-modes/) (2021)

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_compositing_and_blending>

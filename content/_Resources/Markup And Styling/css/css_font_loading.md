CSS font loading
================

The **CSS font loading** module describes events and interfaces used for
dynamically loading font resources.

Reference
---------

### Interfaces

- [`fontFace`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace)
    interface
  - [`FontFace()`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/FontFace)
        constructor
  - [`fontFace.family`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/family)
        property
  - [`fontFace.style`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/style)
        property
  - [`fontFace.weight`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/weight)
        property
  - [`fontFace.stretch`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/stretch)
        property
  - [`fontFace.unicodeRange`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/unicodeRange)
        property
  - [`fontFace.variant`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/variant)
        property
  - [`fontFace.featureSettings`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/featureSettings)
        property
  - [`fontFace.variationSettings`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/variationSettings)
        property
  - [`fontFace.display`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/display)
        property
  - [`fontFace.ascentOverride`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/ascentOverride)
        property
  - [`fontFace.descentOverride`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/descentOverride)
        property
  - [`fontFace.lineGapOverride`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/lineGapOverride)
        property
  - [`fontFace.load()`](https://developer.mozilla.org/en-US/docs/Web/API/FontFace/load)
        method (returns a promise)
- [`fontFaceSet`](https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet)
    interface
- [`fontFaceSetLoadEvent`](https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSetLoadEvent)
    event

Guides
------

[CSS font loading API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Font_Loading_API)

:   Overview of the CSS Font Loading API, which provide events and
    interfaces for dynamically loading font resources.

Related concepts
----------------

- CSS [`@font-face`](@font-face.md) at-rule
- CSS [`@font-feature-values`](@font-feature-values.md) at-rule
- [`CSSFontFaceRule`](https://developer.mozilla.org/en-US/docs/Web/API/CSSFontFaceRule)
    interface
- Document
    [`fonts`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fonts)
    property (returns the
    [`FontFaceSet`](https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet)
    object instance)
- WorkerGlobalScope
    [`fonts`](https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/fonts)
    property (returns the
    [`FontFaceSet`](https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet)
    object instance)
- JavaScript
    [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)
    object

Specifications
--------------

  -----------------------------------------------------------------------

Specification
  -----------------------------------------------------------------------

  [CSS Font Loading Module Level 3\
  ](https://drafts.csswg.org/css-font-loading/)

  -----------------------------------------------------------------------

See also
--------

- [CSS fonts](css_fonts.md) module

© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_font_loading>
